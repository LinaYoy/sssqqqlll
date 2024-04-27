# Роговая Ангелина Владимировна ИС-22/9-1

## Описание

Эта база данных разработана для хранения информации о Картинной Галерее. База данных содержит таблицы для хранения информации о художниках, картинах, выставках и их расположении.

![scheme](https://cdn.discordapp.com/attachments/1225378430086942720/1227238698576248832/image.png?ex=662d9cda&is=662c4b5a&hm=02029fa12bda7ee73e8d08bd813adc8d240f48328469027723e140c5cd3035c3&)

### Таблица "Artists" (Художники)

![Table_Artists](https://cdn.discordapp.com/attachments/1148205618965000283/1233651865418207344/image.png?ex=662ddf54&is=662c8dd4&hm=52408d923fbb1d69a9401a83f05b1bd7bb6ac0510f5ebe8801cc13c3f9df6ec7&)

- **Artists_id**: уникальный идентификатор художника (PRIMARY KEY)
- **name**: имя художника (VARCHAR(30))
- **birthday**: дата рождения художника (TEXT)
- **genre**: жанр творчества художника (VARCHAR(30))

Пример вывода записей из таблицы "Artists":
SELECT * FROM Artists;

![Artists](https://cdn.discordapp.com/attachments/1148205618965000283/1233650426117623858/image.png?ex=662dddfd&is=662c8c7d&hm=7ab5134e6f3c176d5c3d62cb54eecd0dc9cb092d54ceeef6c29701a10b2f210d&)

### Таблица "Exposed" (Экспозиции)

![Table_Exposed](https://cdn.discordapp.com/attachments/1148205618965000283/1233651958221635644/image.png?ex=662ddf6a&is=662c8dea&hm=1fb928a49b43510b1174667bc400e47c7aab90d563557fed4708f236146dcd12&)

- **Exposed_id**: уникальный идентификатор экспозиции (PRIMARY KEY)
- **hall**: название зала, где проводится экспозиция (VARCHAR(30))
- **paintings_id**: идентификатор картины, выставленной на экспозиции (FOREIGN KEY REFERENCES Paintings(id))

Пример вывода записей из таблицы "Exposed":
SELECT * FROM Exposed;

![Exposed](https://cdn.discordapp.com/attachments/1148205618965000283/1233650873423368212/image.png?ex=662dde68&is=662c8ce8&hm=1432647197997f6c50b094b179bed9d3487a59f570eac00f399af480473b45b3&)

### Таблица "Expositions" (Выставки)

![Table_Expositions](https://cdn.discordapp.com/attachments/1148205618965000283/1233652053679673354/image.png?ex=662ddf81&is=662c8e01&hm=f43108727e093b09f75fd08aa65a646aed7c1f30493ddf0ddf42b4c3e09b6e38&)

- **Expositions_id**: уникальный идентификатор выставки (PRIMARY KEY)
- **theme**: тема выставки (VARCHAR(30))
- **begining**: дата начала выставки (DATE)
- **ending**: дата окончания выставки (DATE)
- **exposed_id**: идентификатор экспозиции на выставке (FOREIGN KEY REFERENCES Exposed(id))

Пример вывода записей из таблицы "Expositions":
SELECT * FROM Expositions;

![Expositions](https://cdn.discordapp.com/attachments/1148205618965000283/1233651207424446485/image.png?ex=662ddeb7&is=662c8d37&hm=40a789f477439cd8b66eb091efe284036e4fafac43d942187d72ba154eda102c&)

### Таблица "Paintings" (Картины)

![Table_Paintigs](https://cdn.discordapp.com/attachments/1148205618965000283/1233652150693793856/image.png?ex=662ddf98&is=662c8e18&hm=97ac27842f72626e5029206f05824dc5899738a949ec6c5acf30a497af3aa826&)

- **Paintings_id**: уникальный идентификатор картины (PRIMARY KEY)
- **name**: название картины (VARCHAR(30))
- **date_of_writing**: дата написания картины (DATE)
- **artists_id**: идентификатор художника, создавшего картину (FOREIGN KEY REFERENCES Artists(id))

Пример вывода записей из таблицы "Paintings":
SELECT * FROM Paintings;

![Paintings](https://cdn.discordapp.com/attachments/1148205618965000283/1233651527923798078/image.png?ex=662ddf04&is=662c8d84&hm=8bd72b269b1c0075414bc40844bce09ede3ce9c515335ebc6532501cad06af69&)