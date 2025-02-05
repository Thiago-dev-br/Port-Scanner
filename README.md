# Port-Scanner

Introdução
Um scanner de porta é uma ferramenta crucial para profissionais e entusiastas de segurança de rede. Ele permite que você descubra portas abertas, fechadas ou filtradas em um sistema de destino. Neste tutorial, criaremos um scanner de porta básico usando Python.

Pré-requisitos
Antes de mergulharmos no código, garanta que você tenha o Python instalado no seu sistema. Você pode baixá-lo do site oficial do Python ( https://www.python.org/downloads/ ).

Implementação de código
Abaixo está o código Python para nosso scanner de porta simples:

Importe a biblioteca Socket e pyfiglet:

   import socket, pyfiglet

2. Banner

   ascii_banner = pyfiglet.figlet_format("PORT SCANNER")
   print(ascii_banner)


4. Defina a função do scanner de porta:

def  scan_ports ( host_port, start_port, end_port ): 
    print ( f"Examinando portas em {host_port} ..." ) 

        for port in range(start_port, end_port + 1):
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(1)  # Set a connection timeout

        result = sock.connect_ex((host_port, port))

        if result == 0:
            print(f"Port {port} is open")

        sock.close()
        
3. Reúna a entrada do usuário e inicie a varredura:

if __name__ == "__main__":
    target_hosts = input("Enter the host IP address: ")
    start_port = int(input("Enter the starting port: "))
    end_port = int(input("Enter the ending port: "))

    scan_ports(target_hosts, start_port, end_port)

![image](https://github.com/user-attachments/assets/bedd1913-9a43-4209-a9c7-b31431002fdf)

    
Explicação
Criamos uma função chamada scan_portsque recebe o host de destino (endereço IP), a porta inicial e a porta final como argumentos.
Dentro da função, usamos um forloop para iterar pelo intervalo de portas especificado.
Para cada porta, criamos um soquete e tentamos nos conectar a ele usando sock.connect_ex((host, port)).
Se o resultado da conexão for 0 (indicando sucesso), imprimimos que a porta está aberta.
Por fim, fechamos o socket.

Uso
Execute o script no seu terminal ou IDE.
Insira o endereço IP do host de destino.
Especifique os números de porta inicial e final.
O script verificará as portas especificadas e exibirá os resultados.

![image](https://github.com/user-attachments/assets/ffc7d8bf-16ba-4586-a2d7-c30fd622e97b)


