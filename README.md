# espresso
A stateless macOS zsh wrapper for caffeinate.

## Getting Started
1. Download the espresso script.
2. Navigate to the save directory in your terminal and run: mv espresso ~/.local/bin/
3. Run the following command to view your .zshrc: cat ~/.zshrc
4. Check that the terminal output includes: export PATH="$HOME/.local/bin:$PATH"
5. If it does not,run: echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc

## Usage
espresso [-d|--display] [hours minutes | stop | status]

* **Timed Prevention**: "espresso 2 30" prevents system sleep for 2 hours and 30 minutes. If duration arguments are completely omitted, the script initiates interactive prompts to collect input.
* **Display Control**: Add "-d" or "--display" (e.g., "espresso -d 1 0") to force the display monitor to remain powered on alongside the system background processes.
* **espresso status**: Audits the system to verify whether an active user-owned sleep prevention process is running.
* **espresso stop**: Immediately terminates the active background "caffeinate" process utilizing "pkill". Note: does not kill "caffeinate" processes started outside of espresso.
* **Constraints**: The script actively blocks execution and errors out if another "caffeinate" process is already running under the active user account.
