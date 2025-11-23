# AI News Digest Workflow for n8n

This n8n workflow automates the process of gathering daily AI news, summarizing it using an LLM, and sending a beautifully formatted email digest.

## Features
- **Data Source**: Tavily API (Search & Extract News).
- **Processing**: JavaScript cleaning to remove noise from web scraping.
- **AI Summary**: Google Gemini (or any LLM) to summarize articles into a concise "Daily Selection".
- **Delivery**: Gmail (HTML formatted email with a clean, literary style).

## Prerequisites
To use this workflow, you need:
1.  **n8n**: Self-hosted or Cloud version.
2.  **Tavily API Key**: For searching news.
3.  **Google Gemini API Key**: For generating summaries.
4.  **Gmail Credentials**: OAuth2 credentials to send emails.

## How to use
1.  Download the `n8n_news_digest_workflow.json` file from this repository.
2.  Open your n8n dashboard.
3.  Click **Import workflow** (top right) -> **From File**.
4.  Configure your credentials in the `Tavily`, `Google Gemini`, and `Gmail` nodes.
5.  Update the **Email Digest to Subscriber** node:
    - Change `To Email` to your recipient address.
    - Change `CC Email` (optional).
6.  Activate the workflow!

### 🔐 关于隐私信息的清理说明

我在上面的 JSON 中做了以下具体的脱敏处理，**这不会影响代码的导入功能**：

1.  **Gmail 节点**:
    * `sendTo`: 修改为 `your-email@example.com`。
    * `ccList`: 修改为 `cc-email@example.com`。
    * `credentials.id`: 修改为 `xxxxxxx`。
2.  **Tavily 节点**:
    * `credentials.id`: 修改为 `xxxxxxx`。
3.  **Gemini 节点**:
    * `credentials.id`: 修改为 `xxxxxxx`。
4.  **Meta 信息**:
    * `instanceId`: 修改为 `xxxxxxx`（这个 ID 会暴露你的 n8n 安装实例，必须删除）。

**为什么这样改还可以导入？**
n8n 导入时，如果发现 JSON 中的 `id` 对应的凭证在你的本地不存在，它会**保留节点结构**，但会在界面上显示凭证缺失（红色警告）。使用者只需要点开节点，从下拉菜单选择他们自己配置好的 `Tavily account` 或 `Gmail account` 即可。这是分享 n8n workflow 的标准做法。
