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

Neste código, a função verificar_parenteses utiliza uma pilha para verificar se os parênteses na string estão balanceados. 
Ela percorre a string e, sempre que encontra um parêntese aberto, o adiciona à pilha. Q
uando encontra um parêntese fechado, verifica se o topo da pilha corresponde ao parêntese aberto correspondente. 
Se não corresponder, os parênteses estão desbalanceados. Caso contrário, continua verificando os próximos parênteses. 
No final, se a pilha estiver vazia, significa que todos os parênteses foram corretamente balanceados.
