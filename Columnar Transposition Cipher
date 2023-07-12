import math

def encryptMessage(msg, key):
    cipher = ""
    msg_len = float(len(msg))
    msg_lst = list(msg) + ['_'] * int(math.ceil(msg_len / len(key)) * len(key) - msg_len)
    matrix = [msg_lst[i:i + len(key)] for i in range(0, len(msg_lst), len(key))]
    for k in key:
        cipher += ''.join([row[key.index(k)] for row in matrix])
    return cipher

def decryptMessage(cipher, key):
    msg = ""
    msg_len = float(len(cipher))
    msg_lst = list(cipher)
    matrix = [[None] * len(key) for _ in range(int(math.ceil(msg_len / len(key))))]
    msg_indx = 0
    for k in key:
        for j in range(int(math.ceil(msg_len / len(key)))):
            matrix[j][key.index(k)] = msg_lst[msg_indx]
            msg_indx += 1
    msg = ''.join(sum(matrix, []))
    return msg.replace('_', '')

if __name__ == "__main__":
    msg = input("Enter the message: ")
    key = input("Enter the key: ")
    cipher = encryptMessage(msg, key)
    print("Encrypted Message: {}".format(cipher))
    decrypted_msg = decryptMessage(cipher, key)
    print("Decrypted Message: {}".format(decrypted_msg))
