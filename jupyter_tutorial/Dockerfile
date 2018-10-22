FROM continuumio/miniconda3

RUN /opt/conda/bin/conda config --add channels conda-forge \
    && /opt/conda/bin/conda upgrade conda -y --quiet \
    && /opt/conda/bin/conda upgrade --all -y --quiet \
	&& /opt/conda/bin/conda install \
				jupyter \
				ipywidgets \
				bqplot \
				ipyvolume \
				ipyleaflet \
				pythreejs \
				ipyevents \
			-y --quiet \
	&& /opt/conda/bin/conda install -c wwt pywwt -y --quiet \
	&& /opt/conda/bin/conda update --all -y --quiet \
	&& /opt/conda/bin/ipython kernel install --name widgets-tutorial --display-name widgets-tutorial --sys-prefix \
	&& mkdir /opt/notebooks \
	&& cd /opt/notebooks \
	&& git clone https://github.com/jupyter-widgets/tutorial.git

EXPOSE 8888/tcp

CMD ["/opt/conda/bin/jupyter", \
	"notebook", \
	"--allow-root", \
	"--notebook-dir='/opt/notebooks'", \
	"--ip=0.0.0.0", \
	"--port=8888", \
	"--no-browser"]