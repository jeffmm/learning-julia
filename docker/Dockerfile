FROM manifoldai/orbyter-ml-dev:3.3
WORKDIR /build

ENV JULIA_PATH=/usr/local/julia
ENV PATH $JULIA_PATH/bin:$PATH

# Install Julia
RUN curl -fL -o julia.tar.gz "https://julialang-s3.julialang.org/bin/linux/x64/1.6/julia-1.6.1-linux-x86_64.tar.gz" && \
	mkdir "$JULIA_PATH" && \
	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1 && \
	rm julia.tar.gz && \
    julia -e 'import Pkg; Pkg.add("IJulia")' && \
    rm -rf ~/.cache

WORKDIR /
RUN rm -rf /build
