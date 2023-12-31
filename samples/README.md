# librga IM2D API 示例代码说明

​	该目录下为librga IM2D API示例代码，包含常见的图像缩放、裁剪、旋转、Blit、alpha混合等操作的示例代码。

## 目录说明

├── **im2d_api_demo**：IM2D API快速演示DEMO<br/>
├── **im2d_slt**：slt测试工具<br/>
├── **allocator_demo**：内存分配器相关示例代码<br/>
│   └── **src**
│       ├── **rga_allocator_1106_cma_demo.cpp**：RV1106没有搭载IOMMU，须分配物理连续内存调用RGA，该平台CMA节点路径与其他平台不同。<br/>
│       ├── **rga_allocator_dma32_demo.cpp**：使用dma_heap分配4G以内内存空间的内存（不保证物理连续）调用RGA。<br/>
│       ├── **rga_allocator_dma_cache_demo.cpp**：使用dma_heap分配cacheable的内存调用RGA。<br/>
│       ├── **rga_allocator_dma_demo.cpp**：使用dma_heap分配内存调用RGA。<br/>
│       ├── **rga_allocator_drm_demo.cpp**：使用DRM分配内存调用RGA。<br/>
│       ├── **rga_allocator_drm_phy_demo.cpp**：使用DRM分配物理连续的内存调用RGA。<br/>
│       ├── **rga_allocator_graphicbuffer_demo.cpp**：使用GraphicBuffer分配4G内存空间以内的内存调用RGA。<br/>
│       └── **rga_allocator_malloc_demo.cpp**：使用malloc分配虚拟地址调用RGA。<br/>
├── **alpha_demo**：alpha混合、叠加相关示例代码<br/>
│   └── **src**
│       ├── **rga_alpha_3channel_demo.cpp**：调用RGA实现三通道alpha叠加。<br/>
│       ├── **rga_alpha_colorkey_demo.cpp**：调用RGA实现colorkey。<br/>
│       ├── **rga_alpha_demo.cpp**：调用RGA实现双通道alpha叠加。<br/>
│       ├── **rga_alpha_osd_demo.cpp**：调用RGA实现常见OSD场景<br/>
│       └── **rga_alpha_yuv_demo.cpp**：调用RGA实现RGBA图像与YUV图像alpha叠加。<br/>
├── **async_demo**：异步模式相关示例代码<br/>
├── **config_demo**：线程全局配置相关示例代码<br/>
│   └── **src**
│       ├── **rga_config_single_core_demo.cpp**：指定核心执行当前RGA任务。<br/>
│       └── **rga_config_thread_core_demo.cpp**：当前线程均指定核心执行RGA任务。<br/>
├── **copy_demo**：图像搬运、拷贝相关示例代码<br/>
│   └── **src**
│       ├── **rga_copy_demo.cpp**：调用RGA实现图像拷贝。<br/>
│       ├── **rga_copy_fbc_demo.cpp**：调用RGA实现FBC图像拷贝。<br/>
│       ├── **rga_copy_tile8x8_demo.cpp**：调用RGA实现tile8*8图像拷贝。<br/>
│       ├── **rga_copy_splice_demo.cpp**：调用RGA实现图像拼接。<br/>
│       └── **rga_copy_splice_task_demo.cpp**：批处理方式调用RGA实现图像拼接。<br/>
├── **crop_demo**：图像裁剪、拼接相关示例代码<br/>
│   └──** src**
│       ├── **rga_crop_demo.cpp**：调用RGA实现图像裁剪。<br/>
│       └── **rga_crop_rect_demo.cpp**：调用RGA实现裁剪源图像并输出到目标图像上某一区域。<br/>
├── **cvtcolor_demo**：图像格式转换、色域转换相关示例代码<br/>
│   └── **src**
│       ├── **rga_cvtcolor_demo.cpp**：调用RGA实现图像格式转换。<br/>
│       ├── **rga_cvtcolor_csc_demo.cpp**：调用RGA指定色域空间转换配置实现图像格式转换。<br/>
│       └── **rga_cvtcolor_gray256_demo.cpp**：调用RGA实现256阶灰度图转换。<br/>
├── **fill_demo**：图像填充、画框相关示例代码<br/>
│   └── **src**
│       ├── **rga_fill_demo.cpp**：调用RGA实现颜色填充。<br/>
│       ├── **rga_fill_rectangle_demo.cpp**：调用RGA实现矩形框绘制。<br/>
│       ├── **rga_fill_rectangle_array_demo.cpp**：调用RGA实现多个矩形框绘制。<br/>
│       ├── **rga_fill_rectangle_task_demo.cpp**：批处理方式调用RGA实现矩形框绘制。<br/>
│       └── **rga_fill_rectangle_task_array_demo.cpp**：批处理方式调用RGA实现多个矩形框绘制。<br/>
├── **mosaic_demo**：马赛克遮盖相关示例代码<br/>
├── **padding_demo**：padding相关示例代码<br/>
├── **resize_demo**：图像缩放相关示例代码<br/>
│   └── **src**
│       ├── **rga_resize_demo.cpp**：调用RGA实现图像缩放。<br/>
│       ├── **rga_resize_rect_demo.cpp**：调用RGA实现源图像缩放并输出到目标图像指定区域。<br/>
│       └── **rga_resize_uv_downsampling_demo.cpp**：调用RGA实现YUV422均值降采样到YUV420。<br/>
├── **rop_demo**：ROP运算相关示例代码<br/>
├── **transform_demo**：图像变换相关示例代码<br/>
│   └── **src**
│       ├── **rga_transform_flip_demo.cpp**：调用RGA实现图像镜像。<br/>
│       ├── **rga_transform_rotate_demo.cpp**：调用RGA实现图像旋转。<br/>
│       └── **rga_transform_rotate_flip_demo.cpp**：调用RGA实现图像镜像同事旋转。<br/>
├── **utils**：示例代码中使用的第三方引用、通用工具代码<br/>
└── **sample_file**：演示代码使用图像数据文件<br/>

## 编译说明

​	本仓库示例代码支持CMAKE编译，可以通过修改toolchain_*.cmake文件以及编译脚本实现快速编译。

### 工具链修改

- **Android NDK（build for android）**

​	参考librga源码目录下**toolchains/toolchain_android_ndk.cmake**写法，修改NDK路径、Android版本信息等。

| 工具链选项                          | 描述                                         |
| ----------------------------------- | -------------------------------------------- |
| CMAKE_ANDROID_NDK                   | NDK编译包路径                                |
| CMAKE_SYSTEM_NAME                   | 平台名，默认为Android                        |
| CMAKE_SYSTEM_VERSION                | Android版本                                  |
| CMAKE_ANDROID_ARCH_ABI              | 处理器版本                                   |
| CMAKE_ANDROID_NDK_TOOLCHAIN_VERSION | 工具链选择（clang/gcc）                      |
| CMAKE_ANDROID_STL_TYPE              | NDK C++库的链接方式（c++_static/c++_shared） |

- **Linux（buildroot/debian）**

​	参考librga源码目录下**toolchains/toolchain_linux.cmake**写法，修改工具链路径、名称。

| 工具链选项     | 描述       |
| -------------- | ---------- |
| TOOLCHAIN_HOME | 工具链目录 |
| TOOLCHAIN_NAME | 工具链名称 |

### 编译脚本修改

​	修改samples目录或需要编译的示例代码目录下**cmake_*.sh**，指定toolchain路径。

| 编译选项       | 描述                                                         |
| -------------- | ------------------------------------------------------------ |
| TOOLCHAIN_PATH | toolchain的绝对路径，即《工具链修改》小节中修改后的toolchain_*.cmake文件的绝对路径 |
| LIBRGA_PATH    | 需要链接的librga.so的绝对路径，默认为librga cmake编译时的默认打包路径 |
| BUILD_DIR      | 编译生成文件存放的相对路径                                   |

### 执行编译脚本

- **Android NDK（build for android）**

```bash
$ chmod +x ./cmake_android.sh
$ ./cmake_android.sh
```

- **Linux（buildroot/debian）**

```bash
$ chmod +x ./cmake_linux.sh
$ ./cmake_linux.sh
```

