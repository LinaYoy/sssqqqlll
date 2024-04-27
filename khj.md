# Роговая Ангелина Владимировна ИС-22/9-1

## Описание

Эта база данных разработана для хранения информации о Картинной Галерее. База данных содержит таблицы для хранения информации о художниках, картинах, выставках и их расположении.

![scheme](https://cdn.discordapp.com/attachments/1225378430086942720/1227238698576248832/image.png?ex=662d9cda&is=662c4b5a&hm=02029fa12bda7ee73e8d08bd813adc8d240f48328469027723e140c5cd3035c3&)

### Таблица "Artists" (Художники)

- **Artists_id**: уникальный идентификатор художника (PRIMARY KEY)
- **name**: имя художника (VARCHAR(30))
- **birthday**: дата рождения художника (TEXT)
- **genre**: жанр творчества художника (VARCHAR(30))

Пример вывода записей из таблицы "Artists":
SELECT * FROM Artists;


### Таблица "Exposed" (Экспозиции)

- **Exposed_id**: уникальный идентификатор экспозиции (PRIMARY KEY)
- **hall**: название зала, где проводится экспозиция (VARCHAR(30))
- **paintings_id**: идентификатор картины, выставленной на экспозиции (FOREIGN KEY REFERENCES Paintings(id))

Пример вывода записей из таблицы "Exposed":
SELECT * FROM Exposed;


### Таблица "Expositions" (Выставки)

- **Expositions_id**: уникальный идентификатор выставки (PRIMARY KEY)
- **theme**: тема выставки (VARCHAR(30))
- **begining**: дата начала выставки (DATE)
- **ending**: дата окончания выставки (DATE)
- **exposed_id**: идентификатор экспозиции на выставке (FOREIGN KEY REFERENCES Exposed(id))

Пример вывода записей из таблицы "Expositions":
SELECT * FROM Expositions;


### Таблица "Paintings" (Картины)

- **Paintings_id**: уникальный идентификатор картины (PRIMARY KEY)
- **name**: название картины (VARCHAR(30))
- **date_of_writing**: дата написания картины (DATE)
- **artists_id**: идентификатор художника, создавшего картину (FOREIGN KEY REFERENCES Artists(id))

Пример вывода записей из таблицы "Paintings":
SELECT * FROM Paintings;
