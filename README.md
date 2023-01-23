# Current Portfolio

Current portfolio filled with my current activities. Displays most of my current and relevant work. Contact me for any inquiries or work.

def isBalanced(self, s):
        pair = {"]": "[", ")": "(", "}": "{"}
        stck = []

        # check pair if only string is even length
        if len(s) % 2 == 0:
            for i in s:
                # left brackets push to stack
                if i in "([{":
                    stck.append(i)

                # right bracket with empty stack
                elif len(stck) == 0 and i in ")}]":
                    return "NO"

                # right bracket with elements in stack
                elif len(stck) != 0 and i in ")]}" and pair[i] != stck.pop():
                    return "NO"

            # after processing stack empty
            if len(stck) == 0:
                return "YES"
            else:
                return "NO"

        # odd length
        else:
            return "NO"
