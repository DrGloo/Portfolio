# Current Portfolio

Current portfolio filled with my current activities. Displays most of my current and relevant work. Contact me for any inquiries or work.

def isBalanced(self, s):
        pair = {"]": "[", ")": "(", "}": "{"}
        stck = []

        for (int i = 0; i < expressions.length; i++) {
            Stack<Character> stack = new Stack<>();
            String str = expressions[i];

            for (int j = 0; j < str.length(); j++) {
                char c = str.charAt(j);
                if (c == '<') {
                    stack.push(c);
                } else {
                    if (!stack.isEmpty()) {
                        char stackChar = stack.peek();
                        if (stackChar == '<') {
                            stack.pop();
                        } else {
                            stack.push(c);
                        }
                    } else {
                        stack.push(c);
                    }

                }
            }

            if (stack.isEmpty()) {
                maxReplacements[i] = 1;
            } else {
                int maxReplacement = maxReplacements[i];
                for (int rCount = 0; rCount < maxReplacement; rCount++) {
                    if (!stack.isEmpty()) {
                        char stackChar = stack.peek();
                        if (stackChar == '>') {
                            stack.pop();
                        }
                    }
                }
                if (stack.isEmpty())
                    maxReplacements[i] = 1;
                else
                    maxReplacements[i] = 0;
            }


        }

        return maxReplacements;
    }
