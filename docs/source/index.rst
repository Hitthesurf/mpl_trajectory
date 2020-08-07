.. mpl_trajectory documentation master file, created by
   sphinx-quickstart on Thu Aug  6 14:22:54 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

   
Welcome to mpl_trajectory's documentation!
==========================================

mpl_trajectory helps to plot particle trajectories as animations in matplotlib.
It can show show 3D trajectories by using the third axis as colour.
It can output a static graph or animation of the trajectories.

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

Install
=======
You can use pip

.. code-block:: sh

    pip install mpl-trajectory
	
	
Spyder
------
You must run

.. code-block:: python

	%matplotlib qt

The graph will pop up in a window
	
Jupyter Notebook
----------------
You can run

.. code-block:: python

	%matplotlib qt

The graph will pop up in a window

Or

.. code-block:: python

	%matplotlib notebook
	
This will make the animation or graph appear in the cell bellow.
	
	
Saving
------
If you want to save animations you must have ffmpeg for your system.


Code Documentation
==================
.. automodule:: mpl_trajectory
	:members:
	

Examples
========
Run these setup lines to get all the libraries needed

.. code-block:: python

	from mpl_trajectory import trajectory
	import numpy as np
	import matplotlib as mpl
	import matplotlib.pyplot as plt
	%matplotlib qt
	
	plt.style.use('dark_background')

.. code-block:: python

	x1 = np.linspace(0,40,1500)
	y1 = -5*np.sin(x1)
	dydx_1 = -5*np.cos(x1)

	x2 = np.linspace(0,40,1500)
	y2 = 5*np.sin(x1)
	dydx_2 = 5*np.cos(x1)

	Traj = trajectory()
	Traj.plot3D(x1,y1, dydx_1)
	Traj.plot3D(x2,y2, dydx_2)
	
	
.. code-block:: python

	Traj.ShowAnimation(with_color = True, z_axis=[-5,5], link_data = [[1,2]])
	
.. image:: https://raw.githubusercontent.com/Hitthesurf/mpl_trajectory/master/Examples/GIF/Sine_Wave_example.gif?raw=true
  :width: 600
  :alt: Could not find animation
	
.. code-block:: python

	theta = np.linspace(0,18*np.pi,1500)
	r = np.linspace(0,9,1500)

	x = r*np.cos(theta)
	y = r*np.sin(theta)

	Traj_2 = trajectory()
	Traj_2.plot3D(x,y)
	

.. code-block:: python

	Traj_2.ShowAnimation(follow_mass = -3, size = 9)
	
.. image:: https://raw.githubusercontent.com/Hitthesurf/mpl_trajectory/master/Examples/GIF/Spiral_Motion_Example.gif?raw=true
  :width: 600
  :alt: Could not find animation
	
.. code-block:: python

	Traj_2.ShowStatic(with_color = True)
	
.. image:: https://raw.githubusercontent.com/Hitthesurf/mpl_trajectory/master/Examples/PNG/Static_Spiral_with_color.png?raw=true
  :width: 600
  :alt: Could not find image

GitHub/PyPi
===========

GitHub: https://github.com/Hitthesurf/mpl_trajectory	

Pypi: https://pypi.org/project/mpl-trajectory/