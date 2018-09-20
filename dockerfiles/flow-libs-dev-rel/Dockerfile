FROM flow123d/base-build
MAINTAINER Jan Hybs
ENV LANG C.UTF-8

# Build-time metadata as defined at http://label-schema.org
ARG BUILD_DATE
ARG VCS_REF
ARG VERSION=1.0
ARG BUILD_TYPE=Release

ARG LIB_MPICH=3.2.0
ARG LIB_YAMLCPP=0.5.2
ARG LIB_PETSC=3.6.1
ARG LIB_ARMADILLO=3.4.3
ARG LIB_BDDCML=2.4.0
ARG LIB_URL=http://ciflow.nti.tul.cz/static/packages

LABEL org.label-schema.build-date="$BUILD_DATE" \
      org.label-schema.name="Flow123d" \
      org.label-schema.description="Transport Processes in Fractured Media" \
      org.label-schema.url="http://flow123d.github.io/" \
      org.label-schema.vcs-ref="$VCS_REF" \
      org.label-schema.vcs-url="https://github.com/flow123d/flow123d" \
      org.label-schema.vendor="Technical University of Liberec" \
      org.label-schema.version="$VERSION" \
      org.label-schema.schema-version="1.0"
      
# install yamlcpp, petsc, armadillo and bddcml
RUN echo "Downloading and installing custom libraries" \
 && wget -qO /tmp/YAMLCPP-${LIB_YAMLCPP}.deb "${LIB_URL}/YAMLCPP_${LIB_YAMLCPP}_${BUILD_TYPE}/YAMLCPP_${LIB_YAMLCPP}.deb" \
 && wget -qO /tmp/PETSC-${LIB_PETSC}.deb "${LIB_URL}/PETSC_${LIB_PETSC}_${BUILD_TYPE}/PETSC_${LIB_PETSC}.deb" \
 && wget -qO /tmp/ARMADILLO-${LIB_ARMADILLO}.deb "${LIB_URL}/ARMADILLO_${LIB_ARMADILLO}_${BUILD_TYPE}/ARMADILLO_${LIB_ARMADILLO}.deb" \
 && wget -qO /tmp/BDDCML-${LIB_BDDCML}.deb "${LIB_URL}/BDDCML_${LIB_BDDCML}_${BUILD_TYPE}/BDDCML_${LIB_BDDCML}.deb" \
 && dpkg -i /tmp/*.deb \
 && rm -rf /tmp/*.deb

# edit env variables so libraries can be found
ENV PETSC_DIR="/usr/lib/petsc/" \
    BDDCML_ROOT="/usr/lib/bddcml_blopex/bddcml/Release" \
    Armadillo_ROOT_HINT="/usr/lib/armadillo/Release" \
    YamlCpp_ROOT_HINT="/usr/lib/yamlcpp/Release"
