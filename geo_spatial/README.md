# sparkgeo/geospatial-base

This Docker Image is a base for use cases that require common python geospatial libraries. The list of libraries installed is as follows:

+ GDAL 2.1.1
+ Cython 0.24
+ Boto 2.40.0
+ OpenCV 2.4.8
+ Numpy 1.8.2
+ Scipy 0.13.3
+ Matplotlib 1.5.1
+ Scikit-learn 0.17.1
+ PyProj 1.9.5.1
+ Scikit-image 0.12.3
+ Protobuf 2.6.1
+ Imutils 0.3.6
+ Yapps 2.2.0
+ Profilehooks 1.8.1
+ Fiona 1.6.4
+ Shapely 1.5.15
+ Descartes 1.0.2
+ Pillow 2.9.0
+ Psycopg2 2.6.1
+ Jinja2 2.8
+ Awscli 1.10.28
+ Gbdxtools 0.2.6

## Run

```
$ docker run -it --name runner tdgp/sdk_application_runner:latest /bin/bash
```

### Verify packages:

```
python -c "import osgeo.gdal; print osgeo.gdal.__version__"
python -c "import Cython; print Cython.__version__"
python -c "import boto; print boto.__version__"
python -c "import cv2; print cv2.__version__"
python -c "import numpy; print numpy.__version__"
python -c "import scipy; print scipy.__version__"
python -c "import matplotlib; print matplotlib.__version__"
python -c "import sklearn; print sklearn.__version__"
python -c "import pyproj; print pyproj.__version__"
python -c "import skimage; print skimage.__version__"
python -c "import google.protobuf"
python -c "import imutils"
python -c "import yapps; print yapps.__version__"
python -c "import profilehooks; print profilehooks.__version__"
python -c "import fiona; print fiona.__version__"
python -c "import shapely; print shapely.__version__"
python -c "import descartes"
python -c "import PIL"
python -c "import psycopg2; print psycopg2.__version__"
python -c "import jinja2; print jinja2.__version__"

```

## Inheritors

* [cloud-harness](https://github.com/TDG-Platform/cloud-harness)
