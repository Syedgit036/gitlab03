# PROGRAM 5

## Cross-Site Scripting Attack (XSS)

### Using OWASP ZAP to Identify XSS Script

### Solution

## Step 1

Open the following webpage in Firefox and copy the URL:

```text
http://testphp.vulnweb.com
```

## Step 2

- Open OWASP ZAP application(zaproxy).
- Select:

```text
Automated Scan
```

- Paste the URL.
 ```text
Search for **Cross-Site Scripting Attack** in the **Alert** section.
```
## Step 3

If the option is not found:

Go to:

```text
POST: search.php(test)
```

Then:

```text
Active Action → New Scan
```

Select:

```text
POST: search.php(test)
```

Click:

```text
Advanced Options
```

Under **Input Vectors**, enable:

```text
✔ URL Path
✔ HTTP Header
✔ Cookie Data
✔ All Request
```

Then:

```text
Press Start Scan
```

- Once the scan is completed, go to the **Alert** section.
- Select:

```text
Cross-Site Script (Reflected)
```

- Double-click on the file.
- Select and copy the URL.
- Open Firefox and paste the URL in a new tab.

### Output

The script gets executed and returns a dialog box stating:

```text
"1"
```

## Result

Successfully identified a Cross-Site Scripting (XSS) vulnerability using OWASP ZAP and verified its execution through the reflected XSS alert.
