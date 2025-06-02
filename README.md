	import random
	import string
	def generate_password(length=12, use_upper=True, use_digits=True, use_special=True):
		characters = string.ascii_lowercase
		if use_upper:
			characters += string.ascii_uppercase
		if use_digits:
			characters += string.digits
		if use_special:
			characters += string.punctuation
		if not characters:
			raise ValueError("No character sets selected.")
		return ''.join(random.choice(characters) for _ in range(length))
	if __name__ == "__main__":
		length = int(input("Enter password length: "))
		password = generate_password(length)
		print("Generated password:", password)
