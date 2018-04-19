# Script generated with Bloom
pkgdesc="ROS - This package configures the move_base stack and makes use of the gmapping and amcl algorithms to move the rb1_base robot"
url='http://ros.org/wiki/rb1_base_2dnav'

pkgname='ros-kinetic-rb1-base-2dnav'
pkgver='1.0.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-amcl'
'ros-kinetic-gmapping'
'ros-kinetic-map-server'
'ros-kinetic-message-runtime'
'ros-kinetic-move-base'
'ros-kinetic-robot-pose-ekf'
'ros-kinetic-rviz'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=rb1_base_2dnav
source=()
md5sums=()

prepare() {
    cp -R $startdir/rb1_base_2dnav $srcdir/rb1_base_2dnav
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

