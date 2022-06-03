MinIO Integrated Library for Spring Boot
-------
This library provides utilities that make it easy to integrate MinIO storage into a spring boot project

Feature List:
* [Upload Multipartfile](#upload-multipartfile)
* [Upload Bytes](#Upload-Bytes)
* [Upload String](#Upload-String)
* [Remove File](#Remove-File)
* [Get File](#Get-File)

Quick start
-------
* Just add the dependency to an existing Spring Boot project
```xml
<dependency>
    <groupId>com.atviettelsolutions</groupId>
    <artifactId>vts-kit-ms-minio-integrated</artifactId>
    <version>1.0.0</version>
</dependency>
```

* Then, add the following properties to your `application-*.yml` file.
```yaml
vtskit:
  minio:
    server: http://<host>:<port>
    access-key: <access-key>
    secret-key: <secret-key>
    bucket: <bucket>
    auto-create-bucket: true
```

* Finally, declare `MinioService` object
```java
@Autowired
private MinioService minioService;
```

Usage
-------
##### Upload MultipartFile
```java
ObjectWriteResponse rsUpload = minioService.uploadMultipartFile(file);
```
##### Upload Bytes
```java
UploadResult  upload= uploadBytes(String fileName, byte[] bytes, String contentType)
```
##### Upload String
```java
UploadResult  upload= uploadString(String content)
```
##### Remove File
```java
void removeFile(String filePath)
```
##### Get File
```java
Byte[] file= getFile(String filePath)
```

Build
-------
* Build with Unittest
```shell script
mvn clean install
```

* Build without Unittest
```shell script
mvn clean install -DskipTests
```

Contribute
-------
Please refer [Contributors Guide](CONTRIBUTING.md)

License
-------
This code is under the [MIT License](https://opensource.org/licenses/MIT).

See the [LICENSE](LICENSE) file for required notices and attributions.
