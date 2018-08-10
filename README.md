安装
```
npm i -save dropzone-puge
或
yarn add dropzone-puge
```

使用
```
<template lang="pug">
  <div>
    <Dropzone @getFile="upload" accept=".csv, application/vnd.openxmlformats-officedocument.spreadsheetml.sheet, application/vnd.ms-excel"></Dropzone>
  </div>
</template>

<script>
import Dropzone from 'dropzone-puge'
export default {
  components: {
    Dropzone
  },
  methods: {
    upload (e) {
      console.log(e)
    }
  }
}
</script>
```

## 参数

| 参数        | 含义         | 类型  | 是否必须  |
| ----------- |:-------------:| -----:| -----:|
|accept| 允许上传的文件类型 | String | true |

## 事件

| 参数        | 含义         | 类型  |
| ----------- |:-------------:| -----:|
|getFile| 文件选择事件 | event |
