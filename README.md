## Education
2018 - 2021 The August Witkowski 5th High School in Cracow

2021 - AGH University

## Projects I currently work on
1.[Chess engine](https://github.com/AGH-Narzedzia-Informatyczne-2021-2022/mknl)

## My sample code
```python
          def fen_update_add_current(list_fen, target_file, fen_file, piece, i):
        left_space = target_file - fen_file
        right_space = 0

        if i + 1 != len(list_fen):
            if list_fen[i + 1] == '/':
                right_space = 8 - (target_file + 1)
            elif list_fen[i].isnumeric():
                right_space = int(list_fen[i]) - (left_space + 1)

        help_fen = list_fen[:(i + 1)]

        if left_space != 0:
            help_fen[i] = str(left_space)
            help_fen.append(piece)
        else:
            help_fen[i] = piece

        if right_space != 0:
            help_fen.append(str(right_space))

        help_fen += list_fen[(i + 1):]
        list_fen = help_fen

        return list_fen
```


