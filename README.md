## Education
2018 - 2021 The August Witkowski 5th High School in Cracow

2021 - AGH University

## Projects I currently work on
1.[Chess engine](https://github.com/AGH-Narzedzia-Informatyczne-2021-2022/mknl)

## My sample code
```markdown
      def fen_update(self, rank, file, target_rank, target_file):
        piece = str(self.chess_board[rank][file])
        added_current = False

        fen_rank = 7
        fen_file = 0
        i = 0

        list_fen = [self.fen[i] for i in range(len(self.fen))]

        while i < len(list_fen):
            if list_fen[i] == '/':
                fen_rank -= 1
                fen_file = 0
            elif list_fen[i].isnumeric():
                space = int(list_fen[i])

                if not added_current and fen_rank == target_rank:
                    if fen_file + int(list_fen[i]) > target_file:
                        added_current = True
                        length = len(list_fen)

                        list_fen = self.fen_update_add_current(list_fen, target_file, fen_file, piece, i)

                        i += len(list_fen) - length

                fen_file += space
            else:
                if fen_rank == rank and fen_file == file:
                    length = len(list_fen)

                    if list_fen[i - 1].isnumeric() and list_fen[i + 1].isnumeric():
                        new_space = int(list_fen[i - 1]) + int(list_fen[i + 1]) + 1
                        list_fen[i - 1] = str(new_space)
                        list_fen = list_fen[:i] + list_fen[(i + 2):]
                    elif list_fen[i - 1].isnumeric():
                        list_fen[i - 1] = str(int(list_fen[i - 1]) + 1)
                        list_fen = list_fen[:i] + list_fen[(i + 1):]
                    elif list_fen[i + 1].isnumeric():
                        list_fen[i + 1] = str(int(list_fen[i + 1]) + 1)
                        list_fen = list_fen[:i] + list_fen[(i + 1):]
                    else:
                        list_fen[i] = '1'

                    i += len(list_fen) - length

                if fen_rank == target_rank and fen_file == target_file and not added_current:
                    added_current = True
                    length = len(list_fen)

                    list_fen = self.fen_update_add_current(list_fen, target_file, fen_file, piece, i)

                    i += len(list_fen) - length

                fen_file += 1

            i += 1

        self.fen = ""
        for i in range(len(list_fen)):
            self.fen += list_fen[i]
        print(self.fen)
```


