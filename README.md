# Python Allow List Update

## Project Description
This project showcases an algorithm designed to enhance network security in a healthcare environment. Specifically, it dynamically updates an allow list of IP addresses that are permitted access to sensitive data. By using Python, the algorithm ensures that unauthorized access is prevented by removing IP addresses listed in a predefined remove list. The solution is designed to be efficient, secure, and easy to integrate into existing systems.

The script leverages Python's file handling capabilities to read the allow list from a file, modifies it by removing unwanted entries, and writes back the updated list. This process ensures real-time updates and integrity of the access control system. The approach is suitable for organizations that need to regularly modify access lists as part of their cybersecurity protocols.

## Features
- **File Handling:** Opens, reads, and writes files securely using Python's `with` statement.
- **Dynamic List Management:** Converts the allow list from a string to a list for efficient manipulation.
- **Iterative Matching:** Iterates through a remove list and dynamically removes matching entries from the allow list.
- **Real-Time Updates:** Automatically updates the allow list file with the revised IPs.

## Code Overview

### 1. Open the Allow List File
```python
# Open the allow list file
import_file = "allow_list.txt"
with open(import_file, "r") as file:
    ip_addresses = file.read()
```
**Description**:
- The `import_file` variable contains the name of the allow list file.
- The `with` statement ensures that the file is automatically closed after reading.
- `.read()` is used to load the file content into the `ip_addresses` variable as a string.

### 2. Convert the String to a List
```python
# Convert the string of IP addresses into a list
ip_addresses = ip_addresses.split()
```
**Description**:
- The `.split()` method breaks the string into individual IP addresses, creating a list where each element is an IP address.

### 3. Remove IPs from the Allow List
```python
# List of IPs to remove
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Iterate and remove IPs
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
```
**Description**:
- `remove_list` contains the IP addresses to be removed from the allow list.
- The `for` loop iterates through each IP in the `remove_list` and checks if it exists in `ip_addresses`.
- `.remove()` removes the IP from the allow list if it is found. The algorithm assumes that there are no duplicate IPs in the list, ensuring safe use of `.remove()`.

### 4. Update the Allow List File
```python
# Convert the updated list back to a string
ip_addresses = "
".join(ip_addresses)

# Write the updated list to the file
with open(import_file, "w") as file:
    file.write(ip_addresses)
```
**Description**:
- `.join()` converts the updated list back into a string, with each IP address placed on a new line for better readability.
- The `with open()` statement opens the file in write mode (`"w"`), replacing the existing contents with the updated allow list.



## Summary
This project demonstrates how Python can be used to manage access control in dynamic environments. By reading, processing, and updating an allow list of IP addresses, the algorithm ensures that unauthorized users are removed promptly. The use of Python's core features, such as file handling, list manipulation, and iterative loops, makes this solution both efficient and reliable.

