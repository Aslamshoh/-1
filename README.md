лабо 1

def to_hex(number):
    return hex(number)[2:]


def num_to_words(number):
    ones = ["", "один", "два", "три", "четыре", "пять", "шесть", "семь", "восемь", "девять"]
    teens = ["", "одиннадцать", "двенадцать", "тринадцать", "четырнадцать", "пятнадцать", "шестнадцать", "семнадцать",
             "восемнадцать", "девятнадцать"]

    if 1 <= number <= 9:
        return ones[number]
    elif 11 <= number <= 19:
        return teens[number - 10]
    elif number == 10:
        return "десять"
    elif 20 <= number <= 29:
        return f"двадцать {ones[number - 20]}"
    else:
        return ""


count = 0
max_hex = 0

for i in range(1, 0x3163A):
    hex_str = to_hex(i)

    if len(hex_str) == int(hex_str[0], 16):
        count += 1
        max_hex = i

max_hex_in_words = " ".join([num_to_words(int(ch, 16)) for ch in to_hex(max_hex)])

print(f"Максимальное число: {max_hex_in_words.capitalize()}, количество подходящих чисел: {count}.")





Максимальное число: Четыре пятнадцать пятнадцать пятнадцать, количество подходящих чисел: 4369.
