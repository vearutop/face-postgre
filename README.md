# Face index with PostgreSQL

A small demo based on [`ageitgey/face_recognition`](https://github.com/ageitgey/face_recognition/tree/master/examples)

## Setup

Deps:

```
pip install py-postgresql face_recognition opencv-python
```

Start PostgreSQL 9.6 in docker or natively

```
docker-compose up -d
```

Initialize DB

```
python db.py
```

## Usage 

Add images to index

```
python face-add.py <image.jpg>
```

```
python face-add.py ../lfw/Bill_Clinton/Bill_Clinton_0009.jpg 
Found 1 faces in the image file ../lfw/Bill_Clinton/Bill_Clinton_0009.jpg
- Face #0 found at Left: 86 Top: 96 Right: 175 Bottom: 186


python face-add.py ../lfw/John_Malkovich/John_Malkovich_0001.jpg 
Found 1 faces in the image file ../lfw/John_Malkovich/John_Malkovich_0001.jpg
- Face #0 found at Left: 76 Top: 86 Right: 165 Bottom: 176


python face-add.py ../lfw/Bill_Gates/Bill_Gates_0006.jpg 
Found 1 faces in the image file ../lfw/Bill_Gates/Bill_Gates_0006.jpg
- Face #0 found at Left: 67 Top: 80 Right: 175 Bottom: 187

```

Search for face by image

```
python face-find.py <image.jpg>
```

```
python face-find.py ../lfw/John_Malkovich/John_Malkovich_0003.jpg 
Found 1 faces in the image file ../lfw/John_Malkovich/John_Malkovich_0003.jpg
- Face #0 found at Left: 67 Top: 68 Right: 175 Bottom: 175
[('../lfw/John_Malkovich/John_Malkovich_0001.jpg',)]


python face-find.py ../lfw/Bill_Clinton/Bill_Clinton_0002.jpg 
Found 1 faces in the image file ../lfw/Bill_Clinton/Bill_Clinton_0002.jpg
- Face #0 found at Left: 86 Top: 86 Right: 175 Bottom: 176
[('../lfw/Bill_Clinton/Bill_Clinton_0009.jpg',)]
```