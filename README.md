# Analysis-of-the-Disk-Structure-using-Sleuth-Kit
## NAME: ENBANATHAN V
## REG NO: 212224220027
## AIM:
To analyze the disk structure of a given disk image using Sleuth Kit tools in Kali Linux.

## REQUIREMENTS
- **Operating System**: Windows 10/11 or Kali Linux
- **Tools**:  
  - [The Sleuth Kit for Windows](https://sleuthkit.org/)  
  - Optional GUI: [Autopsy Forensic Browser](https://www.autopsy.com/)
- **Test Data**: Disk image file (`disk.dd`, `disk.img`, `.E01`)

## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Disk Image / Physical Disk] --> B[mmls - Partition Analysis]
    B --> C[fsstat - File System Metadata]
    C --> D[fls - File Listing]
    D --> E[icat - File Recovery]
    E --> F[Recovered Data / Metadata Report]
```
## DESIGN STEPS:
### Step 1:
- Obtain or create a disk image file (e.g., disk.dd) to analyze.
- Open the terminal in Kali Linux.

### Step 2:
Use Sleuth Kit tools like:
 - mmls → Examine the partition layout.
 - fsstat → View file system details.
 - fls → Get file listing.
 - icat → Recover files using inode numbers.
### Step 3:
Interpret the output to understand:
 - Partition table layout
 - File system metadata (block size, creation time, etc.)
 - Deleted and allocated files
 - Inode-based file recovery

## PROGRAM:
Sleuth Kit Disk Analysis Commands
### Partition Analysis
```bash
mmls disk.dd
```
### File System Metadata
```bash
fsstat -o 2048 disk.dd
```
### File Listing
```bash
fls -o 2048 disk.dd
```
### File Recovery
```bash
icat -o 2048 disk.dd 4 > recovered_file.txt
```
- Recovers the file associated with inode 4.
## SAMPLE WORKFLOW (Windows)
```bash
# Step 1: View partitions
mmls.exe C:\forensics\disk.dd

# Step 2: View file system details
fsstat.exe -o 2048 C:\forensics\disk.dd

# Step 3: List files
fls.exe -r -o 2048 C:\forensics\disk.dd

# Step 4: Recover a file
icat.exe -o 2048 C:\forensics\disk.dd 6 > C:\forensics\image.jpg
```
## OUTPUT:
Disk Structure Analysis Results
<img width="625" height="410" alt="EX 2" src="https://github.com/user-attachments/assets/0d227e2f-35f1-4f10-889a-eadfca98769c" />
<img width="518" height="461" alt="EX2 2" src="https://github.com/user-attachments/assets/5670885e-269b-4944-9ac2-777ebe1b33ef" />
<img width="637" height="462" alt="EX2 3" src="https://github.com/user-attachments/assets/b13841ec-fbd0-4898-a143-a6132578fa2e" />
<img width="637" height="458" alt="EN2 4" src="https://github.com/user-attachments/assets/d83a631a-cd0f-4499-9bc8-c49de903f550" />

<img width="629" height="456" alt="EX2 5" src="https://github.com/user-attachments/assets/b69d34a4-82a7-4a13-97dd-4d5fb9e366f5" />

<img width="529" height="442" alt="EX2 6" src="https://github.com/user-attachments/assets/faa66f5d-3543-4784-bc95-1ee6cbdbdb34" />

<img width="487" height="451" alt="EX2 7" src="https://github.com/user-attachments/assets/c0142fe6-6f75-472a-baab-edd44831b448" />

<img width="422" height="450" alt="EX2 8" src="https://github.com/user-attachments/assets/ee8c9e74-a3b6-45ff-84d0-c454b6dd6b7c" />

<img width="423" height="217" alt="EX2 9" src="https://github.com/user-attachments/assets/35f7e8ee-4f71-4c9a-8be9-40191b1b876c" />

## RESULT:
The analysis was performed successfully using Sleuth Kit, and the disk structure was understood in detail.
