    n = int(input('Введите количество файлов: '))
    all_files_list = list()
    for i in range(n):
        file_list = list()
        name = input('Введите название файла: ')
        with open(name) as f:
            len_name = f.readlines()
            file_list.append(name)
            file_list.append(len(len_name))
            file_list.append(len_name)
        all_files_list.append(file_list)
    all_files_list.sort(key=lambda x: x[1])

    for file_name, count_string, text in all_files_list:
        with open('text.txt', 'at') as file:
            file.write(f'{file_name}\n')
            file.write(f'{str(count_string)}\n')
            for string in text:
                file.write(string)
            file.write('\n')