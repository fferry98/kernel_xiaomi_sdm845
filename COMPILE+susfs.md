make O=out ARCH=arm64 vendor/xiaomi/mi845_defconfig vendor/debugfs.config vendor/kernelsu.config vendor/xiaomi/beryllium.config

add this to out/.config
CONFIG_KSU_WITH_KPROBES=n
CONFIG_KSU_SUSFS_SUS_SU=n 

make -j$(nproc --all) O=out \
ARCH=arm64 \
CC=clang \
CXX=clang \
CLANG_TRIPLE=aarch64-linux-gnu- \
CROSS_COMPILE=aarch64-linux-android- \
LLVM_IAS=1 \
LLVM=1 \
CROSS_COMPILE_ARM32=arm-linux-androideabi-
