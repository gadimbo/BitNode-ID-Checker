# Seed Generator
# Converts Input To A Number, Integer

def encode_input(user_input):
    # Branch ID 
    char_to_code = {chr(i + 97): f"{i:02}" for i in range(26)}
    char_to_code[' '] = '26'
    
    encoded_string = ""
    
    for char in user_input:
        encoded_value = char_to_code.get(char.lower())
        if encoded_value:
            encoded_string += encoded_value  
    try:
        BitNode = int(encoded_string)
    except ValueError:
        BitNode = 0  
    # Generates The Seed From The Number
    def sum_of_digits(number: int) -> int:
        total = 0
        while number:
            total += number % 10
            number //= 10
        return total
    print(f"Seed: {sum_of_digits(BitNode)}")
    print(f"(BitNode): {encoded_string}")
# Outputs The Seed And The BitNode 
user_input = input("Enter text: ")
encode_input(user_input)



