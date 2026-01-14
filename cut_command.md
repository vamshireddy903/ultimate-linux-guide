The cut command is used to extract specific columns or fields from each line of text.

👉 Mostly used when working with logs, CSV files, and command output.

Basic syntax

    cut OPTION [FILE]

**Common options (most important)**

1️⃣ -d → delimiter

Defines what separates fields (space, colon, comma, etc.)

2️⃣ -f → field number

Specifies which field(s) to extract

3️⃣ -c → character position

Extracts characters by position

**Practical examples (DevOps-style)**

**Example 1: Extract username from /etc/passwd**

    cut -d: -f1 /etc/passwd

: → delimiter  
1 → first field (username)

**Example 2: Extract home directory**
 
    cut -d: -f6 /etc/passwd

Example 3: CSV file

    cut -d, -f2 data.csv

Gets second column.

Example 4: Get port numbers

    ss -tulnp | cut -d: -f2

Example 5: Character-based cut

    echo "DevOpsEngineer" | cut -c1-6


Output:

DevOps
