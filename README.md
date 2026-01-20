# FLAMES
it's just predicting how a couples can be shipped
name1 = input("Enter your name: ").lower()
name2 = input("Enter crush's name: ").lower()

# Logic to remove common characters
for char in name1[:]:
    if char in name2:
        name1 = name1.replace(char, "", 1)
        name2 = name2.replace(char, "", 1)

count = len(name1) + len(name2)
results = ["Friends", "Lovers", "Affection", "Marriage", "Enemies", "Siblings"]

# The "magic" cycle that finds the result
while len(results) > 1:
    split_index = (count % len(results)) - 1
    if split_index >= 0:
        right = results[split_index + 1:]
        left = results[:split_index]
        results = right + left
    else:
        results.pop()

print("Your relationship status is:", results[0])
