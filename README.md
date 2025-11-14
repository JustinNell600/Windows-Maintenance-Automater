
# Windows Maintenance Automater (WMA)

**Windows Maintenance Automater (WMA)** is a personal project designed to automate essential Windows maintenance tasks using simple yet effective scripting. The goal is to streamline system upkeep by running key diagnostic and repair utilities such as `chkdsk`, `sfc /scannow`, and `DISM`, all within a single automated process.

This project not only simplifies Windows maintenance for users but also serves as a hands-on learning experience in scripting and automation using **Batch file programming**.

## 🎯 Project Goals

* **Automation:** Create a unified script that executes multiple maintenance operations with minimal user input.
* **System Health:** Help maintain Windows integrity and performance by routinely checking for and repairing system issues.
* **Learning Focus:** Deepen my understanding of the **Batch scripting language**, Windows command-line utilities, and automation workflows.
* **Scalability:** Build a foundation that can later be expanded with advanced features such as logging, progress indicators, or even a graphical interface.

## 🧩 Why This Project Exists

Windows maintenance often requires running multiple commands individually — which can be repetitive and time-consuming. WMA simplifies this process by combining these essential tasks into a single script, ensuring that your PC stays healthy with minimal effort.

It’s also a way for me to improve my scripting skills while creating something genuinely useful for everyday maintenance or client work.

## 🐜 Debugging
Encountered a Problem? Contact Me! <br/>
If you want to debug yourself though here's some codes that you'll see that can help you

This is WMA's Error Code System a.k.a **_E_** <br/>
**_E_** has various code that detect when certain things went right or wrong, as of E1.0 it only show's the outcome of each command, but as time goes on **_E_** will become a powerfull tool to self debug and fix the entire WMA system
<ul>
<li>
 **S01**<br/>
This is the `chkdsk` success code. Getting this code means chkdsk completed and either found errors that could be resolved or found zero errors
</li>
  
<li>
### E01
This is the `chkdsk` error code. Getting this code means chkdsk completed and found some errors which couldn't be resolved. WMA will automatically start running a `chkdsk /r /f` to resolve this
</li>

<li>
### S02
This is the `sfc /scannow` success code. Getting this code means sfc /scannow completed and either found errors that could be resolved or found zero errors
</li>

<li>
### E02
This is the `sfc /scannow` error code. Getting this code means sfc /scannow completed and found some errors which couldn't be resolved. WMA will procceed with asking the user if they would like to immediatly run a `DISM /Online /Cleanup-Image /Restorehealth` to attempt to fix these problems
</li>

<li>
#### S02a
This is the `DISM R` success code. The `DISM R` section is a minor section as a part of the `sfc /scannow` section meant to potentially solve any problems when an error in the sfc scan cannot be fixed by the original scan. Getting this code means that WMA has recognized the user's input and has started the `DISM /Online /Cleanup-Image /Restorehealth`
</li>

<li>
### S03
This is the `DISM /Online /Cleanup-Image /Checkhealth` success code. Getting this code means DISM Checkhealth completed and found no component store corruption
</li>

<li>
### E03
This is the `DISM /Online /Cleanup-Image /Checkhealth` error code. Getting this code means DISM Checkhealth completed and found sthat the component store is repairable. WMA will procceed a `DISM /Online /Cleanup-Image /Restorehealth` to attempt to fix these corruptions
</li>
</ul>
## **_E_** Version History
E1.0.0 - First Official Release of the **_E_** system
