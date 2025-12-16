I'm currently using a Mac as my main computer, but also have a Linux machine that I use for heavy lifting, but also for backups. Setting up SSH key-based authentication allows rsync to work seamlessly without password prompts, making backing up and file synchronisation much more convenient. This is particularly useful for automated scripts and frequent manual transfers. It's what I use to ensure that I have a second copy of every file I download, and to keep my music collection in sync, and helps maintain that illusion that all my computers are actually _one_ computer.

## Configuration

### 1. Generate SSH Key on Mac (if you don't have one)

First, check if you already have an SSH key:

```bash
ls -la ~/.ssh/id_*.pub
```

If you don't have a key, generate one:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press Enter to accept the default file location, and optionally set a passphrase (leave empty for truly passwordless, or use ssh-agent for security with convenience).

### 2. Copy Your Public Key to the Linux Server

Use `ssh-copy-id` to copy your public key to the server:

```bash
ssh-copy-id username@server_hostname_or_ip
```

You'll need to enter your password one last time. This command copies your public key to `~/.ssh/authorized_keys` on the server.

**Alternative method** (if `ssh-copy-id` isn't available):

```bash
cat ~/.ssh/id_ed25519.pub | ssh username@server "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"
```

### 3. Test the Connection

Try connecting via SSH without a password:

```bash
ssh username@server_hostname_or_ip
```

If it works without asking for a password, you're all set.

### 4. Use rsync

Now you can use rsync without password prompts:

```bash
# Example: sync a local directory to remote server
rsync -avz /path/to/local/directory/ username@server:/path/to/remote/directory/

# Example: sync from remote server to local
rsync -avz username@server:/path/to/remote/directory/ /path/to/local/directory/
```

#### Common Options for rsync

- `-a` : archive mode (preserves permissions, timestamps, etc.)
- `-v` : verbose output
- `-z` : compress data during transfer
- `-h` : human-readable output
- `--delete` : delete files in destination that don't exist in source
- `--exclude='pattern'` : exclude files matching pattern
- `-n` or `--dry-run` : show what would be transferred without actually doing it

## Troubleshooting

If you still get password prompts:

1. **Check permissions on the server:**
   ```bash
   chmod 700 ~/.ssh
   chmod 600 ~/.ssh/authorized_keys
   ```

2. **Verify SSH config allows key authentication** (on server):
   Check sshd_config for:
   ```
   PubkeyAuthentication yes
   ```

3. **Check SELinux** (if applicable on server):
   ```bash
   restorecon -R -v ~/.ssh
   ```

