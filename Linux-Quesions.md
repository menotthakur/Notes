# Unix Production Support Interview Questions and Answers

## 1. How do you monitor the server resources if inadvertently high traffic is reported?
- **Answer:**
  - We normally use the `sar` command (System Activity Report) for monitoring server resources.
  - Additionally, we have GUI system monitoring tools to keep a real-time check on request load and memory usage.

## 2. How do you monitor your logs while investigating a high severity problem?
- **Answer:**
  - Look for errors in the last N minutes when the issue occurred.
  - If the issue is still occurring intermittently, use the `tail` command to monitor logs for different application server instances.
  - **Command:** 
    ```bash
    tail -f /path/to/logfile
    ```

## 3. How to display and set the class path in Unix?
- **Answer:**
  - To display the current class path variable:
    ```bash
    echo $CLASSPATH
    ```
  - To delete the class path variable:
    ```bash
    unset CLASSPATH
    ```
  - To set a new class path variable:
    ```bash
    export CLASSPATH=/path/to/directory
    ```

## 4. What is the use of redirection and pipe?
- **Answer:**
  - **Redirection:** Directs output to another device or file or gets input from another device or file other than the console.
  - **Pipe:** Directs the output of one command as the input of another.

## 5. How to find the count of a particular exception in a particular log file?
- **Answer:**
  - Use the `grep` command with the `-c` option to count occurrences.
  - **Command:**
    ```bash
    grep -c "pattern" /path/to/logfile
    ```

## 6. How to ignore the case from the previous question of grep?
- **Answer:**
  - To ignore case, add the `-i` option before `-c`.
  - **Command:**
    ```bash
    grep -ic "pattern" /path/to/logfile
    ```

## 7. How to search for the exception count if the log file is zipped?
- **Answer:**
  - Use `zgrep` to search within zipped files.
  - **Command:**
    ```bash
    zgrep -ic "exception" /path/to/zippedfile.gz
    ```

## 8. What is the use of egrep?
- **Answer:**
  - `egrep` is used to find multiple strings in a file using extended regular expressions.
  - **Command:**
    ```bash
    egrep "string1|string2" /path/to/file
    ```

## 9. What command to be used if I need to find something in the rolling logs?
- **Answer:**
  - Use `tail -f` combined with `grep` to search in rolling logs.
  - **Command:**
    ```bash
    tail -f /path/to/logfile | grep "string"
    ```

## 10. What is the use of the sar command?
- **Answer:**
  - The `sar` command is used to monitor various system loads, CPU activity, memory device load, etc.
  - **Command:**
    ```bash
    sar -u 1 5  # Displays CPU usage every second for 5 times
    ```

## 11. How to check all processes running on the system?
- **Answer:**
  - Use the `ps` command.
  - **Command:**
    ```bash
    ps -a
    ```

## 12. List some of the commonly used network commands in Unix.
- **Answer:**
  - `ssh` - Remote login
  - `ping` - Test connectivity
  - `wget` - Download files
  - `ftp` - File transfer protocol
  - `finger` - Information gathering
  - Other commands include `sftp`, `scp`, etc.

---

Thank you for reading! Please subscribe to the channel for more helpful content.# Unix Production Support Interview Questions and Answers

## 1. How do you monitor the server resources if inadvertently high traffic is reported?
- **Answer:**
  - We normally use the `sar` command (System Activity Report) for monitoring server resources.
  - Additionally, we have GUI system monitoring tools to keep a real-time check on request load and memory usage.

## 2. How do you monitor your logs while investigating a high severity problem?
- **Answer:**
  - Look for errors in the last N minutes when the issue occurred.
  - If the issue is still occurring intermittently, use the `tail` command to monitor logs for different application server instances.
  - **Command:** 
    ```bash
    tail -f /path/to/logfile
    ```

## 3. How to display and set the class path in Unix?
- **Answer:**
  - To display the current class path variable:
    ```bash
    echo $CLASSPATH
    ```
  - To delete the class path variable:
    ```bash
    unset CLASSPATH
    ```
  - To set a new class path variable:
    ```bash
    export CLASSPATH=/path/to/directory
    ```

## 4. What is the use of redirection and pipe?
- **Answer:**
  - **Redirection:** Directs output to another device or file or gets input from another device or file other than the console.
  - **Pipe:** Directs the output of one command as the input of another.

## 5. How to find the count of a particular exception in a particular log file?
- **Answer:**
  - Use the `grep` command with the `-c` option to count occurrences.
  - **Command:**
    ```bash
    grep -c "pattern" /path/to/logfile
    ```

## 6. How to ignore the case from the previous question of grep?
- **Answer:**
  - To ignore case, add the `-i` option before `-c`.
  - **Command:**
    ```bash
    grep -ic "pattern" /path/to/logfile
    ```

## 7. How to search for the exception count if the log file is zipped?
- **Answer:**
  - Use `zgrep` to search within zipped files.
  - **Command:**
    ```bash
    zgrep -ic "exception" /path/to/zippedfile.gz
    ```

## 8. What is the use of egrep?
- **Answer:**
  - `egrep` is used to find multiple strings in a file using extended regular expressions.
  - **Command:**
    ```bash
    egrep "string1|string2" /path/to/file
    ```

## 9. What command to be used if I need to find something in the rolling logs?
- **Answer:**
  - Use `tail -f` combined with `grep` to search in rolling logs.
  - **Command:**
    ```bash
    tail -f /path/to/logfile | grep "string"
    ```

## 10. What is the use of the sar command?
- **Answer:**
  - The `sar` command is used to monitor various system loads, CPU activity, memory device load, etc.
  - **Command:**
    ```bash
    sar -u 1 5  # Displays CPU usage every second for 5 times
    ```

## 11. How to check all processes running on the system?
- **Answer:**
  - Use the `ps` command.
  - **Command:**
    ```bash
    ps -a
    ```

## 12. List some of the commonly used network commands in Unix.
- **Answer:**
  - `ssh` - Remote login
  - `ping` - Test connectivity
  - `wget` - Download files
  - `ftp` - File transfer protocol
  - `finger` - Information gathering
  - Other commands include `sftp`, `scp`, etc.

---

Thank you for reading! Please subscribe to the channel for more helpful content.
