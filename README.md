# plupload-antd-react

- plupload-antd-React is a component that integrates plupload and ant-design to upload large file fragments
- This component uses Ant-Design to implement a style similar to its Upload component
- This component supports custom Settings for upload file sizes, types, supported formats, and fragment sizes
- Configure file information callbacks after upload for subsequent operations


# Basic usage

## Installation

```javascript
npm i plupload-antd-react
```

## Example

### Import

```javascript
import BigPlUpload from 'plupload-antd-react'
```

### use in page

```javascript
<BigPlUpload
  getFileList={(fileList) => {
    console.log(fileList);
  }}
  chunk_size={'10kb'}
  autoUpload={true}
  buttonSelect={'上传文件'}
  maxSize={'5M'}
  maxLength={5}
  url='/upload'
/>

```

## Option

```
- getFileList   The callback was successfully uploaded
    - fileList  Uploaded file list data
        - name  The file name
        - url   The file path
        - size  The file size
        - response  The return value of the file upload interface
- chunk_size    Example Set the file fragment size. The default unit is byte and other units can be passed in as strings with units
- autoUpload    This value can be set to true or false
                If true, it means that the file is uploaded immediately after selection
                If false, it means that selecting files and uploading files are carried out in two steps
                Currently only true is supported.The case of false will be improved later
- buttonSelect  Select the text of the File button. Default is 'select'
- maxSize       Size limit for a single uploaded file. The default unit is byte and other units can be passed in as strings with units
- maxLength     Maximum number of uploaded files
- url           IP address of the interface for uploading files
- defaultFileList List of files used for the echo.Receiving an array
    -id         A unique identifier
    -name       The file name
    -url        The file path
    -uploaded   This value is always passed true
```

## Version Description

### 1.0.0 ~ 1.0.5

- Realize the function of uploading and slicing files
- You can dynamically set the number of uploaded files, file type, file size, and chunk size
- return the list of uploaded files
- Customize the upload button text and upload path

### 1.0.6 ～ 1.0.7

- Add the file echo function
- Fixed the upload limit failure caused by file echo
- Optimized the style of the list of files uploaded successfully

### 1.0.8

- Fix the problem of not returning to the file list after uploading
- Fix the problem that the list still has values after deleting files

### 1.0.9

- Modify the update condition of the returned file list
- Fixed the problem of resubmitting missing files after multiple file echo

