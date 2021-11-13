---
title:  "Starting RNA Velocity or Trying to Use Scanpy"
date:   2021-11-12 18:10:00 -0800
image: Scanpy_Logo_BrightFG.svg
tags: [research]
---

The first step...trying to get scanpy...

{% highlight python %}
pip install scanpy
{% endhighlight %}

This basically failed... I needed python tables and thank the lord for [this](https://www.lfd.uci.edu/~gohlke/pythonlibs/#pytables)

I can finally start...haha I lied 
{% highlight python %}
c:\users\melton\appdata\local\programs\python\python39\lib\site-packages\tables\__init__.py in <module>
     12 
     13 # Necessary imports to get versions stored on the cython extension
---> 14 from .utilsextension import (
     15     get_pytables_version, get_hdf5_version, blosc_compressor_list,
     16     blosc_compcode_to_compname_ as blosc_compcode_to_compname,

tables\utilsextension.pyx in init tables.utilsextension()

__init__.pxd in numpy.import_array()

ImportError: numpy.core.multiarray failed to import
{% endhighlight %}

okay now for some reason... I am updating my visual studio to 2022, according to [this](https://stackoverflow.com/questions/54366505/importerror-dll-load-failed-while-file-is-in-working-directory)

LOOOOOOOOOOL ok I did when I just used the same link above to install h5py. thank the lord

{% highlight python%}
pip install scanpy
{% endhighlight %}
--> finally worked :)