Face Recognition Service
========================

This [MLHub](https://mlhub.ai) package provides a quick introduction
to the pre-built Face models provided through the face API of
Microsoft Azure's Cognitive Services.

A free Azure subscription allowing up to 5,000 transactions per month
is available from https://azure.microsoft.com/free/.  Once set up
visit https://ms.portal.azure.com and Create a resource under AI and
Machine Learning called Face. Once created you can access the web API
subscription key from the portal. This will be prompted for in the
demo.

Please note that this is *closed source software* which limits your
freedoms and has no guarantee of ongoing availability.

Visit the github repository for more details:
https://github.com/gjwgit/azface

The Python code is based on the [Microsoft Azure Face API
Documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/Face/).

## Usage ##

* To install mlhub (e.g., Ubuntu 18.04 LTS)

  ```console
  $ pip3 install mlhub
  ```

* To install and configure the pre-built model:

  ```console
  $ ml install azface
  $ ml configure azface
  ```

Demonstration
-------------

```console
$ ml demo azface
=============
Face Services
=============

Welcome to a demo of the pre-built models for Face provided through Azure's 
Cognitive Services. This cloud service accepts images and can perform 
various analyses of the images, returning the results locally.

An Azure resource is required to access this service (and to run this
demo). See the README for details of a free subscription. Then you can
provide the key and the endpoint information here.

Please paste your Face API subscription key []: ********************************
Please paste your endpoint []: https://australiaeast.api.cognitive.microsoft.com/face/v1.0

The Azure Face API subscription key and endpoint have been saved to:

  /home/gjw/.mlhub/azface/key.txt

Detecting faces in photo:
  photo/detection/detection2.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface01.png?raw=true)
```console
Detecting faces in photo:
  photo/detection/detection3.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface02.png?raw=true)
```console
Detecting faces in photo:
  photo/detection/detection6.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface03.png?raw=true)
```console
Detecting faces in photo:
  photo/detection/detection1.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface04.png?raw=true)
```console
Detecting faces in photo:
  photo/detection/detection5.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface05.png?raw=true)
```console
Detecting faces in photo:
  photo/detection/detection4.jpg
Please close each image window (Ctrl-w) to proceed.
```
![](azface06.png?raw=true)
```console
Detecting faces in the target photo:
  photo/PersonGroup/Family1-Dad-Bill/Family1-Dad1.jpg

Detecting faces in the candidate photo:
  photo/identification/identification1.jpg

Matching the face No. 0 ...

Please close each image window (Ctrl-w) to proceed.
```
![](azface07.png?raw=true)
```console
To detect faces in provided photos:

  $ ml detect azface
```

Commands
--------

* To detect faces in a photo:

  ```console
  $ ml detect azface
  ```
  
  It will ask for your Azure face API key, endpoint, as well as a URL
  or path of a photo to detect faces.  You also can provide these by
  command line options:
  
  ```console
  $ ml detect azface --key 'xxx' --endpoint 'https://yyy' --photo '~/.mlhub/azface/photo/detection'
  ```

  Key and endpoint can also be stored in a file such as `key.txt`:
  
  ```
  key = 'xxx'
  endpoint = 'https://yyy'
  ```

  And they can be read by:
  
  ```console
  $ ml detect azface --key-file key.txt --photo '~/.mlhub/azface/photo/detection'
  ```

* To find similar faces between two photos:

  ```console
  $ ml similar azface --target xxx.jpg --candidate yyy.jpg --key-file zzz.txt
  ```
  
  Thus all faces in `yyy.jpg` that are similar to the faces in
  `xxx.jpg` will be found.

  **Examples**:

  ```console
  $ ml similar azface --target '~/.mlhub/azface/photo/PersonGroup/Family1-Dad-Bill/Family1-Dad1.jpg' --candidate '~/.mlhub/azface/photo/identification/identification1.jpg'
  $ ml similar azface --target '~/.mlhub/azface/photo/identification/identification1.jpg' --candidate '~/.mlhub/azface/photo/PersonGroup/Family1-Dad-Bill/'
  ```

## Reference ##

* [Quickstart: Create a Python script to detect and frame faces in an image](https://docs.microsoft.com/en-us/azure/cognitive-services/Face/Tutorials/FaceAPIinPythonTutorial)
* [Microsoft Face API: Python SDK & Sample](https://github.com/Microsoft/Cognitive-Face-Python)

