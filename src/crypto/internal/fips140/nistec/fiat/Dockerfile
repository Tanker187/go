# Copyright 2021 The Go Authors. All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.

FROM coqorg/coq:8.13.2@sha256:c802913b275041b7bac68f398f8d52b676c532b9fe432b18423edbba8d13a012

RUN git clone https://github.com/mit-plv/fiat-crypto && cd fiat-crypto && \
    git checkout 23d2dbc4ab897d14bde4404f70cd6991635f9c01 && \
    git submodule update --init --recursive
RUN cd fiat-crypto && eval $(opam env) && make -j4 standalone-ocaml SKIP_BEDROCK2=1

ENV PATH /home/coq/fiat-crypto/src/ExtractionOCaml:$PATH
