## Java Swing application to upload files to FTP server with progress bar
Swing-based application that uploads files from local computer to a remote FTP server. The application looks like this.

![enter image description here](https://raw.githubusercontent.com/Aditya664/Java-Swing-FTP-Client/main/SwingFileUploadFTP%20program.png)

The following diagram describes workflow of the application:

![enter image description here](https://raw.githubusercontent.com/Aditya664/Java-Swing-FTP-Client/main/Swing%20File%20Upload%20FTP%20application%20workflow.png)

The Swing client application connects to the server via FTP protocol to transfer files. The FTP library to be used is [Apache Commons Net](https://commons.apache.org/net).

The following class diagram depicts how the application is designed:

![enter image description here](https://raw.githubusercontent.com/Aditya664/Java-Swing-FTP-Client/main/SwingFileUploadFTP%20class%20diagram.png)

The main classes are:

-   -   `FTPUtility`: implements FTP file upload functionality.
    -   `UploadTask`: executes the file upload task in a background thread other than the Swing’s event dispatcher thread (EDT), so the GUI won’t become freezing.
    -   `SwingFileUploadFTP`: assembles user interface of the application. It allows users to specify FTP server information (host, port, username, password and upload destination), choose a file to be uploaded. It shows a progress bar while the upload is taking place.

For the classes `JFilePicker` and `FileTypeFilter`, its source code can be obtained from article [File picker component in Swing](https://www.codejava.net/java-se/swing/file-picker-component-in-swing). The `FTPException` is a custom exception class.
