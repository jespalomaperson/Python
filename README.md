# Python
### criar interação com email

import win32com.client as Win32
outlook = win32.Dispatch('outlook.applicantion')

### criar email
email = outlook.CreatItem(0)

faturamento = 100
Produtos = 10
Ticket_medio = faturamento / Produtos

### configurar informações do email
email.To = 'jespalomabh@hotmail.com'
email.Subject = 'Email automático do python'
email.HTML.body = f"""

<p> Olá Jessica, aqui é o código pyhton </p>
<p> O faturamento da loja foi de R${faturamento}</p>
<p>Vendemos {Produtos} </p>
<p> e nosso ticket médio foi de R${Ticket_medio}</p>

<p>Abracos</p>
<p>Código Python</p>
"""

email.send()
print('email enviado')
