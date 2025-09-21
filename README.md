## **Yêu cầu xây dựng:**

1. Trình biên dịch C++ hỗ trợ C++17 hoặc mới hơn

2. [Cmake](https://cmake.org/)

3. [Vcpkg](https://vcpkg.io/en/)

4. [Git](https://git-scm.com/)

## **Hướng dẫn xây dựng:**

1. Clone repository:  
	- `git clone https://github.com/BaoBaoTheDev/Black_Hole`
2. CD vào thư mục vừa clone:  
	- `cd ./black_hole` 
3. Cài đặt các phụ thuộc bằng Vcpkg:  
	- `vcpkg install`
4. Lấy đường dẫn file toolchain cmake của vcpkg:  
	- `vcpkg integrate install`  
	- Kết quả sẽ giống như: `CMake projects should use: "-DCMAKE_TOOLCHAIN_FILE=/path/to/vcpkg/scripts/buildsystems/vcpkg.cmake"`
5. Tạo thư mục build:  
	- `mkdir build`
6. Cấu hình project với CMake:  
	- `cmake -B build -S . -DCMAKE_TOOLCHAIN_FILE=/path/to/vcpkg/scripts/buildsystems/vcpkg.cmake`  
	- Dùng đường dẫn toolchain vcpkg từ bước trên
7. Build project:  
	- `cmake --build build`
8. Chạy chương trình:  
	- File thực thi sẽ nằm trong thư mục build

### Thay thế: Cài đặt nhanh trên Debian/Ubuntu

Nếu bạn không muốn dùng vcpkg, hoặc chỉ cần cách nhanh để cài các gói phát triển gốc trên Debian/Ubuntu, cài các gói sau và sau đó chạy các bước CMake bình thường ở trên:

```bash
sudo apt update
sudo apt install build-essential cmake \
	libglew-dev libglfw3-dev libglm-dev libgl1-mesa-dev
