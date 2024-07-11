
We want to share a fundamental feature of our platform: the generation of unique identifiers for uploaded files. This feature uses a hash algorithm linked to the file and base64 to create compact IDs, ensuring uniqueness even if the file is deleted and re-uploaded. Additionally, it helps prevent file duplication by detecting if they already exist in our system.

```python
def generate_file_id(file_content, file_type):
 # Calculate the SHA-256 hash of the file content
 file_hash = hashlib.sha256(file_content).digest()
 # Convert the hash to a Base64 string to reduce the length
 hash_base64 = base64.b64encode(file_hash).decode('utf-8')
 # Delete unwanted symbols and replace them with nothing
 hash_base64_alphanumeric = re.sub(r'[^a-zA-Z0-9]', '', hash_base64)
 # Determine the file prefix based on the file type
 if file_type == "vid":
    prefix = "vid"
 elif file_type == "img":
    prefix = "img"
 elif file_type == "zip":
    prefix = "zip"
 elif file_type == "doc":
    prefix = "doc"
 else:
    logger.error(f"Invalid file type: {file_type}")
    return None
 # Concatenate the prefix with the Base64 hash
 file_id = f"{prefix}-{hash_base64_alphanumeric}"

 return file_id
 ```