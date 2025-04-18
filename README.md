# Atividade-Escolar
Gerador de Qrcode
A ideia é um código curto porem totalmente Funcional

import qrcode

def gerar_qrcode(conteudo, nome_arquivo='qrcode.png'):
    qr = qrcode.QRCode(
        version=1,
        box_size=10,
        border=5
    )
    qr.add_data(conteudo)
    qr.make(fit=True)
    
    img = qr.make_image(fill_color='black', back_color='white')
    img.save(nome_arquivo)
    print(f"QR Code salvo como '{nome_arquivo}'")

def menu():
    print("###### Gerador de QR Code ######")
    print("1. Criar QR Code com URL")
    print("2. Criar QR Code com Texto simples")
    opcao = input("Escolha uma opção (1 ou 2): ")

    if opcao == '1':
        url = input("Digite a URL: ")
        gerar_qrcode(url, 'qrcode_url.png')
    elif opcao == '2':
        texto = input("Digite o texto: ")
        gerar_qrcode(texto, 'Qrcodecriado.png')
        print("seu Qrcode foi criado com sucesso!")
    else:
        print("Opção inválida.")

if __name__ == '__main__':
    menu()

