# DB-practice
: DB-practice-with-SQLite
- DB with SQLite
- DB data handle with Flask-SQLAlchemy

```angular2html
# 파이썬으로 DB 데이터 조회 가능할 수 있는 모듈
$ pip3 install Flask-SQLAlchemy

$ flask shell
$ from app import db, Song
db.create_all()

# 데이터 저장
song = Song(username="추천자", title="노래제목",
artist="가수", image_url="이미지 주소")
db.session.add(song)
db.session.commit()

# 여러 데이터 저장
song1 = Song(username="추천자", title="노래제목1",
artist="가수1", image_url="이미지 주소1")

song2 = Song(username="스파르타", title="노래제목2",
artist="가수2", image_url="이미지 주소2")

song3 = Song(username="스파르타", title="노래제목3",
artist="가수3", image_url="이미지 주소3")
db.session.add(song1)
db.session.add(song2)
db.session.add(song3)

db.session.commit()

# 데이터 저장
Song.query.all()

# 데이터 저장 및 가져오기
song_list = Song.query.all()
song_list[0]
song_list[0].title
song_list[0].artist

# 특정 조건으로 데이터 가져오기
Song.query.filter_by(username='추천자').all()
Song.query.filter_by(id=3).all()
Song.query.filter_by(id=3).first() // 데이터 하나만 조회

# 데이터 변경하기
song_data = Song.query.filter_by(id=4).first()
song_data.title = '변경된제목'
db.session.add(song_data)
db.session.commit()

# 데이터 삭제하기
delete_data = Song.query.filter_by(id=4).first()
db.session.delete(delete_data)
db.session.commit()

```

## Author

```
2024.02.03 ~
Author: Subi Jeong
```