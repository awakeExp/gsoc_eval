# Python Analysis Package for AWAKE

## Evaluation test for GSOC Project

This is the evaluation test for Python Analysis Package for AWAKE. Please fork this repository and complete the steps listed below.

* The test is based on a single hdf file which can be downloaded from [CERNBox](https://cernbox.cern.ch/index.php/s/wk7SN1qt2O7jbrl). This is a public link which should prompt you to download the file. Please contact me if you have issues with the dowload.

* The file name starts with an 19 digit number, which is the UNIX time in nanoseconds. Using the python [datetime](https://docs.python.org/3/library/datetime.html) library and [pytz](http://pytz.sourceforge.net/), convert this number to a python datetime object in both UTC and CERN local time.

* Use the [h5py](http://docs.h5py.org/en/stable/) library to open the hdf file. The file is organized as a directory tree with [groups](http://docs.h5py.org/en/stable/high/group.html) and [datasets](http://docs.h5py.org/en/stable/high/dataset.html). Write a program which explores all branches of the directory tree and identifies all of the datasets in the file. Your program should create a csv file which records the names of all of the groups and datasets, and includes the size, shape and type of  data in each dataset.

* In the hdf file, there is 2D image data stored as a 1D array in the dataset called "/AwakeEventData/XMPP-STREAK/StreakImage/streakImageData". The datasets "/AwakeEventData/XMPP-STREAK/StreakImage/streakImageHeight" and "/AwakeEventData/XMPP-STREAK/StreakImage/streakImageWidth" store information about the height and width of the image. Use [numpy.reshape](https://docs.scipy.org/doc/numpy/reference/generated/numpy.reshape.html) to convert the 1D array into a 2D image. Then, use [scipy.signal.medfilt](https://docs.scipy.org/doc/scipy-0.14.0/reference/generated/scipy.signal.medfilt.html) to filter the image. Finally, use [matplotlib](https://matplotlib.org/) to display the image and save it as a png file.

When you have finished the tasks, add your code, csv file, and png image to the forked repository and make a pull request so that I know to review your work.

## Project Proposal

Your project proposal should address two topics:

- AWAKE has tens of thousands of hdf files containing event data from the experiment. These files are "uneven" in that they do not all contain the same data. Propose a technique for creating a uniform, easily searchable database for AWAKE and writing an API that will allow AWAKE scientists to quickly search for and extract relevant data.

- Once the database has been created, you can contribute to the development of analysis tools for the AWAKE data. This can include image analysis and data visualization tools. There is also an opportunity to use machine learning algorithms to search for correlations in the data, but that is not a requirement for the project.

### If you have any questions, don't hesitate to contact me at [spencer.j.gessner@cern.ch].
