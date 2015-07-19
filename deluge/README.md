# Deluge

Create a directory on your host to persist deluge when you shutdown the container:

    mkdir ~/.deluge

Run the following to start the container

    docker run -d -p 8112:8112 --name deluge -v /Users/YOURUSERNAME/.deluge:/data -v /Users/YOURUSERNAME/Downloads:/root/Downloads ugorelik/deluge
