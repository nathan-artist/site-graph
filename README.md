# Website link graph visualization

![](example.png)

- [my blog post about this project](https://www.cs.cornell.edu/~kt/post/site-graph/)
- [a live example on my website](https://www.cs.cornell.edu/~kt/graph/)

## Commands

```
python site_graph.py --base-url https://napari.org/ --from-data-file crawl.pickle --width 1200 --height 950 --options options.txt
python site_graph.py https://napari.org/stable/plugins/ --base-url https://napari.org/ --options options.txt
```

## Dependencies
python3
- bs4
- pyvis
- networkx
- requests
- scipy

## Running

```
git clone https://github.com/tomlinsonk/site-graph.git
cd site-graph
pip3 install -r requirements.txt
python3 site_graph.py https://www.cs.cornell.edu/~kt/
```

To see site of interest for you, just change the URL.

To see more options, run:
```python3 site_graph.py -h```

Blue nodes are internal pages, green nodes are internal resource files (anything that isn't HTML), orange nodes are external pages, and red nodes are pages with errors. Hover over nodes to see URLs and specific errors (e.g. 404, 500, timeout).

To see a graph of a local files, serve the files using a simple local HTTP server such as [Twisted](https://github.com/twisted/twisted) (in Python), usage: `twistd -no web --path=[path to files]`, or [http-server](https://github.com/http-party/http-server) (in Node.js), usage: `http-server [path to files]`, and use the resulting URL, for example: `python3 site_graph.py http://localhost:8080/`

## Contributing
This code is under a MIT License. Feel free to make pull requests if there are some features you'd like included (or bugs you'd like fixed).
