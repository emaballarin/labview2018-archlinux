# Maintainer:       Emanuele Ballarin <emanuele@ballarin.cc>
# Main Contributor: Tassos Natsakis <7712382@eipieq.com>

_release='2018'
_short_release="${_release:2:4}"
_service_pack='1'
pkgname="labview-${_release}"
pkgver="SP${_service_pack}"
pkgrel=0
pkgdesc='A system-design platform and development environment for a visual programming language from National Instruments. 2018 SP1 version.'
url="https://www.ni.com/labview/release-archive/${_release}/"
arch=('x86_64')
license=("custom:LabVIEW-${_release}")
depends=('xdg-utils' 'hicolor-icon-theme' 'desktop-file-utils' 'shared-mime-info')
makedepends=('sed' 'libarchive')
options=('!strip') # Avoid time consuming operations.
PKGEXT='.pkg.tar' # Do not compress, it's a large package (~1GB).

# The order below IS IMPORTANT!
source=("file://LICENSE.txt"
        "file://PATENTS.txt"
        "file://nicurli-17.0.0-f0.x86_64.rpm"
        "file://nisslcerts-17.0.0-3.0.noarch.rpm"
        "file://nissli-17.0.0-f0.x86_64.rpm"
        "file://nisyscfgi-18.0.0.49152-f0.x86_64.rpm"
        "file://nitargetcfgi-5.0.0.49153-f1.x86_64.rpm"
        "file://labview-2018-appbuild-18.0.1-1.x86_64.rpm"
        "file://labview-2018-core-18.0.1-1.x86_64.rpm"
        "file://labview-2018-desktop-18.0.1-1.x86_64.rpm"
        "file://labview-2018-examples-18.0.1-1.x86_64.rpm"
        "file://labview-2018-exe-18.0.1-1.x86_64.rpm"
        "file://labview-2018-help-18.0.1-1.x86_64.rpm"
        "file://labview-2018-pro-18.0.1-1.x86_64.rpm"
        "file://labview-2018-ref-18.0.1-1.x86_64.rpm"
        "file://labview-2018-rte-18.0.1-1.x86_64.rpm"
        "file://lvsupport2018-cdsim-18.0.0-f1.x86_64.rpm"
        "file://lvsupport2018-cdsimmathscript-18.0.0-f1.x86_64.rpm"
        "file://lvsupport2018-mathscriptrt-18.0.0-f1.x86_64.rpm"
        "file://lvsupport2018-vianalyzer-18.0.0-f0.x86_64.rpm"
        "file://nicurli-18.0.0-f0.x86_64.rpm"
        "file://niexfinder-base-1.0-49.noarch.rpm"
        "file://niexfinder-exe-1.0-49.x86_64.rpm"
        "file://niexfinder-labview-2018-18.0.1-1.noarch.rpm"
        "file://niexfinder-lib-2018-18.0.1-1.x86_64.rpm"
        "file://nijsonmapi-18.0.1-1.noarch.rpm"
        "file://nilvcli-1.1.0.49154-f2.x86_64.rpm"
        "file://nilvcompare-18.0.1-1.noarch.rpm"
        "file://nilvmerge-18.0.1-1.noarch.rpm"
        "file://nipythoninterfacei-18.0.0.49152-f0.x86_64.rpm"
        "file://nisslcerts-18.0.0-3.0.noarch.rpm"
        "file://nissli-18.0.0-f0.x86_64.rpm"
        "file://nisvcloc-18.0.0-1.noarch.rpm"
        "file://nitdmsi-18.0.0.49152-f0.x86_64.rpm"
        "file://labview-2018-rte-18.0.1-2.x86_64.rpm"
        # Manually-repacked patch (in-place)
        "file://LV2018SP1_f1LDevPatch-repacked.tar.gz")

sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP')

package() {
  # Create necessary directories
  mkdir -p "${pkgdir}/etc"
  mkdir -p "${pkgdir}/usr"
  mkdir -p "${pkgdir}/usr/share/licenses/LabVIEW-${_release}"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/48x48/apps"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/128x128/apps"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/48x48/mimetypes"
  mkdir -p "${pkgdir}/usr/share/icons/hicolor/128x128/mimetypes"
  mkdir -p "${pkgdir}/usr/share/applications"
  mkdir -p "${pkgdir}/usr/share/mime/packages"

  # Actually install (i.e. copy) files from the package
  cp -rp "${srcdir}/etc" "${pkgdir}/"
  cp -rp "${srcdir}/usr" "${pkgdir}/"

  # Manually install additional files
  cp "${srcdir}/LICENSE.txt" "${pkgdir}/usr/share/licenses/LabVIEW-${_release}/LICENSE.txt"
  cp "${srcdir}/PATENTS.txt" "${pkgdir}/usr/share/licenses/LabVIEW-${_release}/PATENTS.txt"
  cp "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/icons/48x48/labview.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/labview.png"
  cp "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/icons/48x48/natinst-labview.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/natinst-labview.png"
  cp "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/icons/128x128/labview.png" "${pkgdir}/usr/share/icons/hicolor/128x128/apps/labview.png"
  cp "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/icons/128x128/natinst-labview.png" "${pkgdir}/usr/share/icons/hicolor/128x128/apps/natinst-labview.png"
  for file in "${pkgdir}"/usr/local/natinst/LabVIEW-"${_release}-64"/etc/desktop/icons/48x48/application-x-*.png; do
    cp "$file" ${pkgdir}/usr/share/icons/hicolor/48x48/mimetypes/
    cp "$file" ${pkgdir}/usr/share/icons/hicolor/128x128/mimetypes/
  done
  cp "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/mime/labview.xml" "${pkgdir}/usr/share/mime/packages"

  # Apply specific tweaks
  sed "s,Exec.*,Exec=/usr/local/natinst/LabVIEW-${_release}-64/labview -launch "%F"," "${pkgdir}/usr/local/natinst/LabVIEW-${_release}-64/etc/desktop/apps/natinst-labview64-${_release}.desktop" > "${pkgdir}/usr/share/applications/natinst-labview-${_release}.desktop"

  # In Arch, /usr/lib64 is a symlink of /usr/lib, on x86_64 systems
  mv "${pkgdir}/usr/lib64" "${pkgdir}/usr/lib"

  # Fix some runtime-specific bugs
  cp "${pkgdir}/usr/local/lib64/LabVIEW-2018-64/libNILVRuntimeManager.so.18.0.1" "${pkgdir}/usr/local/lib64/libNILVRuntimeManager.so.18.0.1"
  cp "${pkgdir}/usr/local/lib64/LabVIEW-2018-64/libNILVRuntimeManager.so.18.0.1" "${pkgdir}/usr/local/lib64/libNILVRuntimeManager.so"
  cp "${pkgdir}/usr/local/natinst/niPythonInterface/lib64/libniPythonInterface.so.1.0.0" "${pkgdir}/usr/local/lib64/libniPythonInterface.so.1.0.0"
  cp "${pkgdir}/usr/local/natinst/niPythonInterface/lib64/libniPythonInterface.so.1.0.0" "${pkgdir}/usr/local/lib64/libniPythonInterface.so"
}

# vim:set et sw=2 sts=2:
