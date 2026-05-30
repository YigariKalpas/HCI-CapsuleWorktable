# HCI-RAG
‘环境配置步骤：’
首先通过anaconda新建一个虚拟的python实验环境，再通过pip install安装对应的依赖库，其中Chromas用于高效的向量存储与检索 ，Gradio用作构建可视化交互界面 ，而requests负责向DeepSeek API发送生成请求，再通过huggingface下载对应的嵌入模型（本次使用BAAI/bge-small-zh-v1.5）并本地部署初始化，方便在本地将文档进行向量化切分，最后在deepseek和百度千帆官网得到对应的api作为环境变量实现整体的部署。
依赖包及对应版本：
Package                                  Version
---------------------------------------- -----------
accelerate                               1.13.0
aiohappyeyeballs                         2.6.2
aiohttp                                  3.13.5
aiosignal                                1.4.0
annotated-doc                            0.0.4
annotated-types                          0.7.0
anyio                                    4.13.0
async-timeout                            5.0.1
attrs                                    26.1.0
bcrypt                                   5.0.0
bidict                                   0.23.1
blinker                                  1.9.0
brotli                                   1.2.0
build                                    1.5.0
certifi                                  2026.5.20
charset-normalizer                       3.4.7
chromadb                                 1.5.9
click                                    8.4.1
colorama                                 0.4.6
coloredlogs                              15.0.1
distro                                   1.9.0
durationpy                               0.10
exceptiongroup                           1.3.1
fastapi                                  0.136.3
filelock                                 3.29.0
Flask                                    3.1.3
Flask-SocketIO                           5.6.1
flatbuffers                              25.12.19
frozenlist                               1.8.0
fsspec                                   2026.4.0
googleapis-common-protos                 1.75.0
gradio                                   6.14.0
gradio_client                            2.5.0
groovy                                   0.1.2
grpcio                                   1.80.0
h11                                      0.16.0
hf-gradio                                0.4.1
hf-xet                                   1.5.0
httpcore                                 1.0.9
httptools                                0.7.1
httpx                                    0.28.1
huggingface_hub                          1.16.1
humanfriendly                            10.0
idna                                     3.16
importlib_resources                      7.1.0
itsdangerous                             2.2.0
Jinja2                                   3.1.6
jiter                                    0.15.0
jsonschema                               4.26.0
jsonschema-specifications                2025.9.1
kubernetes                               36.0.0
markdown-it-py                           4.2.0
MarkupSafe                               3.0.3
mdurl                                    0.1.2
mmh3                                     5.2.1
mpmath                                   1.3.0
multidict                                6.7.1
networkx                                 3.4.2
numpy                                    2.2.6
oauthlib                                 3.3.1
onnxruntime                              1.23.2
openai                                   2.38.0
opentelemetry-api                        1.42.1
opentelemetry-exporter-otlp-proto-common 1.42.1
opentelemetry-exporter-otlp-proto-grpc   1.42.1
opentelemetry-proto                      1.42.1
opentelemetry-sdk                        1.42.1
opentelemetry-semantic-conventions       0.63b1
orjson                                   3.11.9
overrides                                7.7.0
packaging                                26.0
pandas                                   2.3.3
pillow                                   12.2.0
pip                                      26.0.1
propcache                                0.5.2
protobuf                                 6.33.6
psutil                                   7.2.2
pybase64                                 1.4.3
pydantic                                 2.13.4
pydantic_core                            2.46.4
pydantic-settings                        2.14.1
pydub                                    0.25.1
Pygments                                 2.20.0
pypdf                                    6.12.2
PyPika                                   0.51.1
pyproject_hooks                          1.2.0
pyreadline3                              3.5.6
python-dateutil                          2.9.0.post0
python-dotenv                            1.2.2
python-engineio                          4.13.2
python-multipart                         0.0.29
python-socketio                          5.16.2
pytz                                     2026.2
PyYAML                                   6.0.3
referencing                              0.37.0
regex                                    2026.5.9
requests                                 2.34.2
requests-oauthlib                        2.0.0
rich                                     15.0.0
rpds-py                                  0.30.0
safehttpx                                0.1.7
safetensors                              0.7.0
semantic-version                         2.10.0
setuptools                               81.0.0
shellingham                              1.5.4
simple-websocket                         1.1.0
six                                      1.17.0
sniffio                                  1.3.1
starlette                                1.1.0
sympy                                    1.14.0
tenacity                                 9.1.4
tokenizers                               0.22.2
tomli                                    2.4.1
tomlkit                                  0.14.0
torch                                    2.12.0
tqdm                                     4.67.3
transformers                             5.9.0
typer                                    0.25.1
typing_extensions                        4.15.0
typing-inspection                        0.4.2
tzdata                                   2026.2
urllib3                                  2.7.0
uvicorn                                  0.48.0
watchfiles                               1.2.0
websocket-client                         1.9.0
websockets                               16.0
Werkzeug                                 3.1.8
wheel                                    0.46.3
wsproto                                  1.3.2
yarl                                     1.24.2

‘知识库说明：’
按照所给文档1-5说明
文档一主要内容以deepseek的信息介绍相关
文档二涉及有关python编程语言特点相关内容
文档三主要内容为人工智能发展简史
文档四仅“1124是全世界小明的生日”一句话用于对特定情况下RAG与LLM区别反应的测试

‘运行指南：’
在运行前将有效api填入对应位置后通过配置好的虚拟环境启动运行后，程序会首先尝试通过embedding模型对所给文档进行拆分和向量化，若已存在对应的向量化生成文件或无文档来源将跳过这一步，通过switch-xx语句进行模式的切换或启用gradio等功能，在选定对应模型以及是否启用RAG模式后可以进行问答。

‘运行效果：’
<img width="958" height="501" alt="屏幕截图 2026-05-25 091640" src="https://github.com/user-attachments/assets/a9c719be-7845-482e-93c9-f5264ad37b56" />
<img width="961" height="280" alt="image" src="https://github.com/user-attachments/assets/4df6f038-20ef-4b23-a5f8-02fb4f5c3722" />
<img width="1919" height="1035" alt="image" src="https://github.com/user-attachments/assets/72a3b023-32ba-470b-b602-22920b1dc3fe" />

