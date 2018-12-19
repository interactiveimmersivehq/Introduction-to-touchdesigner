
### *9.6 External Modules*

One of the underused benefits of Python integration in TouchDesginer is the ability to import third-party Python libraries and use them natively. This includes the ability to use libraries such as the popular Requests or Beautiful Soup libraries. Importing a library is a simple process.

1. Install a 64-bit build of Python. At the time of writing, 3.5 is the latest.

2. Use 'pip' to install your desired packages

3. Open TouchDesigner and go to the 'Edit' menu, and then click on 'Preferences'

4. Find the setting under 'General' called 'Python 64-bit Module Path' and add the path to your 64-bit Python 'site-packages' folder. This folder can be found in your Python installing folder, inside of the 'Lib' folder

5. Inside of TouchDesigner, create a Text DAT, and test the package by using standard 'import' command


It is a good idea to confirm that 'pip' installed the package for the correct version of Python. A common issue users face is that 'pip' is called for a different version of Python than is desired.