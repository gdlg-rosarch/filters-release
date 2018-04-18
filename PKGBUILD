# Script generated with Bloom
pkgdesc="ROS - This library provides a standardized interface for processing data as a sequence of filters. This package contains a base class upon which to build specific implementations as well as an interface which dynamically loads filters based on runtime parameters."
url='http://ros.org/wiki/filters'

pkgname='ros-melodic-filters'
pkgver='1.8.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-catkin>=0.5.68'
'ros-melodic-pluginlib'
'ros-melodic-rosconsole'
'ros-melodic-roscpp'
'ros-melodic-roslib'
'ros-melodic-rostest'
)

depends=('ros-melodic-pluginlib'
'ros-melodic-rosconsole'
'ros-melodic-roscpp'
'ros-melodic-roslib'
)

conflicts=()
replaces=()

_dir=filters
source=()
md5sums=()

prepare() {
    cp -R $startdir/filters $srcdir/filters
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

