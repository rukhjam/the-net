
import sys

# getting input
print("Input content. Ctrl-D or Ctrl-Z ( windows ) to save it.")
contents = []
while True:
    try:
        line = input()
    except EOFError:
        break
    contents.append(line)
#print(contents)

lines = int(contents[0])
#print(lines)

# Checking if lines within constraint
if lines < 0 or lines > 10:
    print("You have provided out of bound number of lines....Exiting")
    sys.exit()

output = []
for i in range(lines):
    if len(contents[i+1]) > 100:
        print("You have provided characters beyond limit...Exiting")
        sys.exit()
    input = contents[i+1]
    modify_input = ""
    reverse = True
    for c in range(len(input)):
        if c == 0:
            modify_input = modify_input + input[c].upper()
            reverse = not reverse
        elif input[c].isalpha():
            if reverse:
                modify_input = modify_input + input[c].upper()
                reverse = not reverse 
            else:
                modify_input = modify_input + input[c].lower()
                reverse = not reverse
        else:
            modify_input = modify_input + input[c]
    output.append(modify_input)

#print(output)
for o in output:
    print(o)
