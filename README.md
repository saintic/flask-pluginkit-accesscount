# AccessCount

IP、PV、Endpoint 统计插件

## Installation

### Development

`pip install git+https://github.com/saintic/flask-pluginkit-accesscount@master`

### PyPi Release

`pip install flask-pluginkit-accesscount`

## Usage

```python
from flask_pluginkit import PluginManager

PluginManager(
    plugin_packages=["flask_pluginkit_accesscount"],
    # If Flask-PluginKit version >= 3.10.0, otherwise pip install it.
    install_packages=dict(pkgs=["flask-pluginkit-accesscount"]),
)
```

## Configuration

Flask Config 配置项

### PLUGINKIT_ACCESSCOUNT_FLUSH_TIMES
设置本地累计请求多少次后刷入redis，int 类型，默认 100

### PLUGINKIT_ACCESSCOUNT_FLUSH_INTERVAL
设置本地累计请求多少秒后刷入redis，int 类型，默认 60

### PLUGINKIT_ACCESSCOUNT_KEY_PREFIX
redis key 前缀，str 类型，默认 pluginkit

### PLUGINKIT_ACCESSCOUNT_REDIS_NAME
redis client 实例连接名称，str 类型，默认 redis，从 g 获取

### PLUGINKIT_ACCESSCOUNT_REDIS_URL
redis 连接地址，str 类型，如果不指定上述NAME，则从该地址连接，两者不能同时缺少。
