#!/usr/bin/env python

import urllib2
import hashlib

#url = 'https://media.readthedocs.org/pdf/requests/latest/requests.pdf'
url = 'http://docs.python.org.ar/tutorial/pdfs/TutorialPython2.pdf'

def descarga(url):
    bufer = bytes(4)
    archivo_remoto = urllib2.urlopen(url)
    hash = hashlib.md5()
    lectura_total = 0

    while True:
        data = archivo_remoto.read(4096)
        lectura_total += 4096
        bufer = bufer + data
        if not data:
            break
        hash.update(data)
    md5 = hash.hexdigest()
    fichero_local = open(md5 + '.pdf', 'w')
    fichero_local.write(bufer)
    fichero_local.close()

descarga(url)
