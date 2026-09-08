# Neps-Windows-Usability-Config
My setup for komorebi+yasb

## How to set this up.
Requirements:
```
  Windows 10+
```

1. Clone this repo.
  ```
    cd C:\Users\<Your User>
    git clone https://github.com/Re3ses/Neps-Windows-Usability-Config.git
  ```

2. Install komorebi, yasb, and whkd
  ```
    winget install --id AmN.yasb
    winget install LGUG2Z.komorebi
    winget install LGUG2Z.whkd
  ```

3. Set environment variables for komorebi 
  [Komorebi Custom Configuration](https://komorebi-starlight.lgug2z.workers.dev/common-workflows/configuration-directory/)

  ```
  # Make sure that Powershell profile exists
  # If not, create one via powershell
  New-Item -ItemType Directory -Force "$HOME\Documents\WindowsPowerShell"
  New-Item -ItemType File -Force "$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"

  # Insert this into the powershell profile:
  `$Env:KOMOREBI_CONFIG_HOME = 'C:\Users\<Your User>\Neps-Windows-Usability-Config\.config\komorebi'`

  # Save the changes and reload the powershell profile
  `. $PROFILE`
  ```

  Add the path to User Environment Variables
  ```
    Environment Variables > User Variables > New 

    # Komorebi
    Variable Name: KOMOREBI_CONFIG_HOME
    Variable Value: C:\Users\<Your User>\Neps-Windows-Usability-Config\.config\komorebi

    # Yasb
    Variable Name: YASB_CONFIG_HOME
    Variable Value: C:\Users\<Your User>\Neps-Windows-Usability-Config\.config\yasb
  ```

4. Enable Autostart
  ```
    # Run in powershell
    komorebic enable-autostart --whkd
    yasbc enable-autostart
  ```

5. Run the programs
  ```
    komorebic start --whkd
    yasbc start
  ```
