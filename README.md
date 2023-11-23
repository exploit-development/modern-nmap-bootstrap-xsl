# Nmap Scan Result Viewer

Have a nice interface for checking the result of your Nmap scans. 

## How to Use

### 1. New Nmap Scan

Add the `modern-nmap-bootstrap.xsl` as a stylesheet to your Nmap scan with the `--stylesheet` argument:

```bash
nmap -sS -T4 -A -sC -oA output --stylesheet https://raw.githubusercontent.com/codesecure-org/modern-nmap-bootstrap-xsl/master/modern-nmap-bootstrap.xsl scanme.nmap.org scanme2.nmap.org
```

Directly open the file `input.xml` with your web browser; it will be formatted correctly. It should look like the `output.html` sample report.

### 2. With a Previously-Run Scan (with XML Output)

If you have a Nmap scan already run, with its output as XML, you can apply the formatting template to it. You'll have two options:

#### a. Convert XML to HTML file

Transform the XML to HTML with the following command:

```bash
xsltproc -o output.html modern-nmap-bootstrap.xsl input.xml
```

Make sure to download the `modern-nmap-bootstrap.xsl` stylesheet beforehand.

#### b. Add the Stylesheet to the XML File

Insert the following line after `<!DOCTYPE nmaprun>` inside the XML file:

```xml
<?xml-stylesheet href="https://raw.githubusercontent.com/codesecure-org/modern-nmap-bootstrap-xsl/master/modern-nmap-bootstrap.xsl" type="text/xsl"?>
```

### Scan Report
![Scan Report](https://raw.githubusercontent.com/codesecure-org/modern-nmap-bootstrap-xsl/main/1.png)

### Detailed Overview
![Detailed Overview](https://raw.githubusercontent.com/codesecure-org/modern-nmap-bootstrap-xsl/main/2.png)

### Summary Table
![Summary Table](https://raw.githubusercontent.com/codesecure-org/modern-nmap-bootstrap-xsl/main/3.png)
