# encryptor

def Input():
    print("Поставлен режим [Шифратор]. Для выхода [0]")
    while True:

        user_encode = input("[] : ")
        user_text = user_encode

        def encode_message():
            encoded_message = ''.join([chr(ord(c) + 1) for c in user_encode])
            mod_encoded_message = encoded_message.replace('л','к').replace('ж','а')

            print("Ваше сообщение: "+user_text+"\nВаше сообщение в шифре: "+mod_encoded_message)

        if user_encode == "0":
            main()
        else:
            encode_message()


def Output():
    print("Поставлен режим [Дешифратор]. Для выхода [0]")
    while True:

        user_decode = input("[] : ")
        user_text = user_decode

        def decoding_message():
            decoded_message = ''.join([chr(ord(c) - 1) for c in user_decode])
            mod_decoded_message = decoded_message.replace('й', 'к').replace('Я', 'е')
            print("Ваше сообщение: "+user_text+"\nВаше сообщение без шифра: "+mod_decoded_message)

        if user_decode == "0":
            main()
        else:
            decoding_message()

        # d0bfd180d0b8d0b2d0b5d182

global menu
def main():

    print("\n==========================================================\n                    Выбор режима :\n---------------------------------------------------------- \n                    |Шифратор [1] \n                    |Дешифратор [2]\n==========================================================")

    menu = input("[] : ")

    if menu == "1":
        Input()

    if menu == "2":
        Output()


if __name__ == '__main__':
    main()

    if menu == "1":
        Input()

    if menu == "2":
        Output()

    if menu != "1" or menu != "2":
        print("Неизвестная команда")
        main()
