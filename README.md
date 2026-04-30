# CNS-ALA-3
NAME:SNEHA MAKWANA ENROLLMENT:240905091021

import hmac
import hashlib

# Shared secret key (must be same for sender & receiver)
secret_key = b"my_secret_key"

# ------------------ SENDER SIDE ------------------
print("🔹 SENDER SIDE")

message = input("Enter message to send: ").encode()

# Generate MAC using HMAC + SHA-256
mac = hmac.new(secret_key, message, hashlib.sha256).hexdigest()

print("Generated MAC:", mac)

# ------------------ RECEIVER SIDE ------------------
print("\n🔹 RECEIVER SIDE")

received_message = message   # Simulating same message received
received_mac = mac           # MAC sent along with message

# Receiver generates MAC again
new_mac = hmac.new(secret_key, received_message, hashlib.sha256).hexdigest()

# Verify MAC
if hmac.compare_digest(received_mac, new_mac):
    print("✅ Message is authentic and not modified")
else:
    print("❌ Message has been tampered")

 <img width="582" height="346" alt="Screenshot 2026-04-30 102645" src="https://github.com/user-attachments/assets/23a98f8e-11d4-4f52-8f53-3943b4bc565c" />


