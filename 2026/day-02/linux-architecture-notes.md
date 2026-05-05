
Linux Architecture (Super Simple)
Think Linux like a company --> '🏢'
1. Kernel (Brain )-->'🧠'
  * Kernel = Boss of the system
  * Controls everything
 # Work: 
   * CPU manage
   * Memory manage
   * File manage
   * Hardware control (keyboard, disk, etc.)
 # Example :
  When you open a file → request goes to Kernel
  __________________________________________________________________________________________________
2. User Space (Employees) -->'👨‍💻'
  * Where you and apps work
  * Cannot directly touch hardware
 # Examples:
  * Chrome
  * vs Code
  * Treminal commands
  # Flow:
    You → App → Kernel → Hardware
____________________________________________________________________________________________________
3. init / systemd (Manager )-->'👨‍💼'
  * First process (PID = 1)
  * Starts everything when system boots
 # Work:
  * Start services (nginx, mysql)
  * Restart failed services
  * Manage background apps
____________________________________________________________________________________________________
 Process Management (Very Important) -->'⚙️'
 🔹 What is Process?
 # Simple:
  A running program
 # Examples:
  * nginx running → process
  * mysql running → process
 # Each process has:
  * PID (Process ID) → unique number
____________________________________________________________________________________________________
🔹 Process Creation
 When program starts:
* Parent creates child using fork()
 # Example:
  Terminal → opens → creates new process
____________________________________________________________________________________________________
 Process States (Easy Way)
 State                         	Meaning
 ---------------------------------------------------------------------------------------------------
 Running (R)	                Currently working
Sleeping (S)	                 Waiting (very common)
Stopped (T)	                      Paused
Zombie (Z)	                      Finished but not cleaned
Dead	                           Fully removed
----------------------------------------------------------------------------------------------------
 # Real example:
 * You open Chrome → Running
 * Chrome waiting → Sleeping
 ___________________________________________________________________________________________________
 systemd (DevOps Hero )
 🔹 What is systemd?
  # Simple:
  A service manager
----------------------------------------------------------------------------------------------------
 🔹 Why important?
 ✅ 1. Auto start services
 # Example:
 * nginx start automatically on boot
 ✅ 2. Restart if crash
 * If app fails → auto restart
 ✅ 3. Logs checking
 * Using journalctl
 ___________________________________________________________________________________________________
 🛠️ Daily Linux Commands (Must Know)
  1. Check processes
    ps aux
  2. Live monitoring
    top
  3. Stop process
     kill <PID> Force stop: kill -9 <PID>
  4. Check service
   systemctl status nginx
   5. Start/Stop service
     systemctl start nginx
     systemctl stop nginx

     6. Logs check
     journalctl -u nginx