FROM brownccv/sh-julia:latest

MAINTAINER Stronghold Help <stronghold-help@brown.edu>


COPY julia_scripts/datasci_pkgs.jl /opt/scripts/
RUN julia -e 'using Pkg; include("/opt/scripts/install_packages.jl"); include("/opt/scripts/datasci_pkgs.jl"); Pkg.update(); install(datasci_pkgs); install(dataset_pkgs);'


#remove pre-compiled libraries as it creates permission errors
RUN rm -rf /opt/julia/share/julia/compiled

#expose notebook and mysql port
EXPOSE 8888 3306
