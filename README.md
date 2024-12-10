# Python Allow List Update

## Project Description
This project involves the creation of an algorithm to manage access control in a healthcare environment. The algorithm updates an allow list of employee IP addresses permitted to access restricted content. It removes IP addresses that appear on a predefined remove list and updates the file with the revised list, ensuring secure access control.

## Features
- Reads the current allow list from a file.
- Identifies and removes IP addresses that are no longer allowed access.
- Updates the allow list file with the revised IP addresses.
- Ensures proper file handling and data integrity.

## Code Overview

### 1. Open the Allow List File
```python
# Open the allow list file
import_file = "allow_list.txt"
with open(import_file, "r") as file:
    ip_addresses = file.read()
```
- Reads the file's contents into a string using the `.read()` method.

### 2. Convert the String to a List
```python
# Convert the string of IP addresses into a list
ip_addresses = ip_addresses.split()
```
- Splits the string into a list of IP addresses for easy manipulation.

### 3. Remove IPs from the Allow List
```python
# List of IPs to remove
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]

# Iterate and remove IPs
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
```
- Iterates through the `remove_list` and removes matching IPs from the `ip_addresses`.

### 4. Update the Allow List File
```python
# Convert the updated list back to a string
ip_addresses = "
".join(ip_addresses)

# Write the updated list to the file
with open(import_file, "w") as file:
    file.write(ip_addresses)
```
- Converts the updated list back to a string and writes it to the allow list file.


## Summary
This algorithm ensures that access control is dynamically updated by modifying an allow list of IP addresses. By using Python's file handling and list manipulation features, the process is efficient and secure.

