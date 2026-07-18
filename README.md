# ai-api-examples

OpenAI 兼容 API 调用示例与开发者接入文档。

## 服务入口

- API Base URL：<https://api.dianfangsihuo.tech/v1>
- API 文档：<https://api.dianfangsihuo.tech/docs>
- 服务主页：<https://api.dianfangsihuo.tech/>
- 店铺入口：<https://pay.ldxp.cn/shop/LSFFTKGZ>

## Python

~~~python
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_API_KEY",
    base_url="https://api.dianfangsihuo.tech/v1",
)

resp = client.chat.completions.create(
    model="YOUR_MODEL",
    messages=[{"role": "user", "content": "你好"}],
)
print(resp.choices[0].message.content)
~~~

## Node.js

~~~js
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: process.env.OPENAI_API_KEY,
  baseURL: "https://api.dianfangsihuo.tech/v1",
});

const result = await client.chat.completions.create({
  model: "YOUR_MODEL",
  messages: [{ role: "user", content: "你好" }],
});
console.log(result.choices[0].message.content);
~~~

## curl

~~~bash
curl https://api.dianfangsihuo.tech/v1/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"YOUR_MODEL","messages":[{"role":"user","content":"你好"}]}'
~~~

## 排查提示

- 401：检查 API Key、前缀和请求头。
- 404：确认 Base URL、路径和模型名称。
- 429：检查额度、并发与限流说明。
- 超时：检查网络、请求体大小和服务状态。

请以 API 文档、店铺页面当前显示的服务说明与计费规则为准。本仓库仅作技术示例与交流，不构成可用性或效果承诺。
