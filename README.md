def postfix_eval(exp):
    stack=[]

    for i in exp:
        if i.isdigit():
            stack.append(int(i))
        else:
            b=stack.pop()
            a=stack.pop()

            if i=='+':
                stack.append(a+b)
            elif i=='*':
                stack.append(a*b)
            elif i=='-':
                stack.append(a-b)
            elif i=='/':
                stack.append(a/b)

    return stack.pop()

exp="54+6*"
print("Expression:",exp)
print("Result:",postfix_eval(exp))

Output:
Expression: 54+6*
Result: 54
