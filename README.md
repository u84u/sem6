PRACTICAL: 1
Forensic imaging and analysistool designed to acquire, create forensic images, and 
perform detailed analysis using FTK imager tool.
Aim: To create a forensically sound image file of a storage device using FTK Imager while 
ensuring data integrity for digital forensic investigation.
System Prerequisites
• Computersystem with Windows Operating System
• FTK Imager installed on the system
• Minimum 4 GB RAM (8 GB recommended)
• Sufficient free disk space to store the forensic image file
• Administrator privileges on the system
Tools Required
• FTK Imager
• Externalstorage device (to store the image file)
About FTK (Forensic Toolkit)
FTK (Forensic Toolkit) is a comprehensive digital forensic software developed by
AccessData. It is widely used by forensic investigators to acquire, analyze, and report 
digital evidence from various storage media. FTK supports in-depth analysis of file
systems, deleted files,system artifacts, and metadata while ensuring evidence integrity.
FTK works closely with FTK Imager, which is used for forensic acquisition. The acquired 
image files are then processed and analyzed in FTK for investigation purposes. The tool 
provides advanced features such as keyword searching, data carving, registry analysis, 
email analysis, and bookmarking of evidence, making it suitable for professional and
academic forensic investigations.
FTK is commonly used in cyber crime investigations, incident response, corporate 
investigations, and academic digital forensics laboratories.

PRACTICAL: 2
Using Forensic Tool: Autopsy.
Aim
To demonstrate the recovery of deleted files using the Autopsy Digital Forensics Tool by 
creating a forensic image with FTK Imager, deleting selected files, and analyzing the image in 
Autopsy.
System Prerequisites
• Computersystem with Windows Operating System
• FTK Imager installed on the system
• Autopsy installed on the system
• Minimum 4 GB RAM (8 GB recommended)
• Sufficient free disk space to store image and case files
• Administrator privileges on the system
Tools Required
• FTK Imager
• Autopsy Digital Forensics Tool
• Externalstorage device or test folder
• Sample test files(documents, images, text files, etc.)
About Autopsy
Autopsy is an open-source digital forensics platform used for analyzing disk images and 
recovering digital evidence. It provides a graphical interface for The Sleuth Kit and allows
investigatorsto examine file systems, recover deleted files, analyze metadata, and generate 
forensic reports. Autopsy is widely used in academic laboratories and professional 
investigations for post-acquisition forensic analysis.
Procedure (Attach Screenshotsfor Each Step)
Step 1: Create Test Files
1. Create a folder on the system (e.g., Test_Evidence).
2. Add five test files of different types (e.g., .txt, .pdf, .jpg, .docx, .png).
Step 2: Create Forensic Image Using FTK Imager
3. Open FTK Imager with administrator privileges.
4. Click File → Create Disk Image.
5. Select Contents of a Folder and choose the Test_Evidence folder.
