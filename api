# api/index.py - 终极“Hello World”测试代码
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/api/', methods=['POST', 'OPTIONS'])
def handler():
    """
    这是一个最简单的测试函数。
    它不读取任何文件，也不调用任何外部API。
    它的唯一目的就是返回一个固定的成功信息。
    """

    # 当浏览器发送 OPTIONS “预检”请求时，直接回复成功。
    # 真正的跨域许可头会由 vercel.json 文件负责添加。
    if request.method == 'OPTIONS':
        return jsonify(status="preflight-check-ok"), 200

    # 当浏览器发送真正的 POST 请求时，回复一个固定的测试成功信息。
    if request.method == 'POST':
        
        # 构造一个假的、写死的成功结果
        test_result = {
            "一级分类": "连接测试成功",
            "二级分类": "Hello World from Vercel",
            "标准问题": "服务器已成功响应",
            "回复内容": "如果您能看到这条消息，代表从凡科页面到Vercel服务器的整条链路已经完全打通！"
        }
        
        # 将这个固定的成功结果返回给前端
        return jsonify(test_result), 200
