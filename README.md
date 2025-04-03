# Connect VSCode remotely to the GPU Server

## Set up SSH (Windows)

- Open PowerShell
- Enter `ssh-keygen -t ed25519`
  - Press enter once
  - If you are asked `Overwrite (y/n)`, enter `n`
  - Otherwise, just press enter at every prompt
- Enter `$u = "alice"`, replacing `alice` with your own GPU Server username
- Enter `type $env:USERPROFILE\.ssh\id_ed25519.pub | ssh $u@gpu-server.dhlab.intra.uni-freiburg.de "cat >> .ssh/authorized_keys"`
  - If you are asked whether you are sure you want to continue, enter `yes`
  - Enter your GPU Sever password
- Optional: Enter `ssh $u@gpu-server.dhlab.intra.uni-freiburg.de "hostname"` to test whether everything worked
  - You should get `gpu-dhlab`

## Set up SSH (Linux and probably also Mac)

- Open a terminal
- Enter `ssh-keygen -t ed25519`
  - Press enter once
  - If you are asked `Overwrite (y/n)`, enter `n`
  - Otherwise, just press enter at every prompt
- Enter `u="alice"`, replacing `alice` with your own GPU Server username
- Enter `ssh-copy-id $u@gpu-server.dhlab.intra.uni-freiburg.de`
  - If you are asked whether you are sure you want to continue, enter `yes`
  - Enter your GPU Sever password
- Optional: Enter `ssh $u@gpu-server.dhlab.intra.uni-freiburg.de "hostname"` to test whether everything worked
  - You should directly get `gpu-dhlab` without being asked for a password

## Configure VSCode

- Install and open VSCode
- Click the `≶` Icon in the bottom left corner
- Select `SSH` or `Connect to Host...`
- Select `Add new SSH Host...`
- Enter `alice@gpu-server.dhlab.intra.uni-freiburg.de`, again replacing `alice` with your own GPU Server username
- Select the highlighted option

