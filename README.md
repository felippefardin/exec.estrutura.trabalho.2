# exec.estrutura.trabalho.2

def verificar_parenteses(string):
    pilha = []
    abertos = ['(', '[', '{']
    fechados = [')', ']', '}']
    
    for char in string:
        if char in abertos:
            pilha.append(char)
        elif char in fechados:
            if not pilha:
                return False
            topo = pilha.pop()
            if abertos.index(topo) != fechados.index(char):
                return False
    
    return not pilha

string1 = "(()()()())"
string2 = "(((())))"
string3 = "(()((())()))"
string4 = "((((((())"
string5 = "()))"
string6 = "(()()(()"

print(verificar_parenteses(string1))  # Saída: True
print(verificar_parenteses(string2))  # Saída: True
print(verificar_parenteses(string3))  # Saída: True
print(verificar_parenteses(string4))  # Saída: False
print(verificar_parenteses(string5))  # Saída: False
print(verificar_parenteses(string6))  # Saída: False
