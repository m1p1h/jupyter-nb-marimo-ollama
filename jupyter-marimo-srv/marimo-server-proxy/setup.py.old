#!/usr/bin/env python3

import os
import setuptools

setuptools.setup(
	name='jupyter-marimo-proxy',
	py_modules=["marimo_proxy"],	
	entry_points={
		'jupyter_serverproxy_servers': [
			'marimo = marimo_proxy:setup_marimoserver',
		]
	},
	install_requires=['jupyter-server-proxy'],
)
