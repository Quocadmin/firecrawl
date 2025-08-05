Firecrawl là gì?
Firecrawl là một dịch vụ API mã nguồn mở, giúp bạn tự động lấy (scrape/crawl) dữ liệu từ bất kỳ website nào, rồi chuyển đổi dữ liệu đó thành dạng sạch, dễ sử dụng (markdown, HTML, structured data, v.v), phù hợp để làm đầu vào cho AI hoặc các ứng dụng khác.
Bạn chỉ cần nhập một đường link (URL), Firecrawl sẽ tự động “bò” vào trang đó và các trang con, lấy nội dung, trả về cho bạn dưới dạng gọn gàng.

Firecrawl dành cho ai?
Lập trình viên AI, muốn lấy dữ liệu sạch từ website để huấn luyện AI, chatbot, tổng hợp dữ liệu,...

Data Engineer, Data Scientist cần lấy dữ liệu website nhanh, sạch, tự động.

Nhà phát triển sản phẩm, nhà nghiên cứu, hoặc bất kỳ ai cần chuyển đổi nội dung website thành dạng dễ dùng cho các ứng dụng, workflow tự động.

Firecrawl làm được gì?
Scrape: Lấy nội dung chính của một trang web (theo các định dạng bạn chọn: markdown, HTML, JSON, screenshot, v.v).

Crawl: Tự động duyệt qua các trang con trong website, lấy toàn bộ dữ liệu liên quan.

Map: Liệt kê ra tất cả các URL (liên kết) có trong một website.

Search: Tìm kiếm nội dung trên web và lấy nội dung chi tiết từ các kết quả.

Extract: Trích xuất dữ liệu có cấu trúc (structured data) từ một hoặc nhiều trang, theo yêu cầu của bạn (có thể dùng prompt, schema).

Tính năng mạnh mẽ của Firecrawl
Kết quả chuẩn cho AI: Dữ liệu trả về dạng markdown, HTML, structured data, screenshot,... phù hợp dùng với LLM (Large Language Model).

Chống bot, vượt xác thực: Có thể vượt qua các kỹ thuật chống bot, đăng nhập, dynamic content, xử lý javascript,...

Tùy chỉnh sâu: Bạn có thể loại trừ thẻ HTML, giới hạn độ sâu crawl, thêm header tuỳ chỉnh, crawl sau đăng nhập,…

Hỗ trợ media: Tự động đọc và trích xuất PDF, hình ảnh, docx,...

Batch & Action: Có thể scrape hàng loạt URL một lúc, tự động thao tác như click, điền form, chờ, chụp ảnh màn hình trước khi lấy dữ liệu.

API đa dạng, dễ dùng: Hỗ trợ Python, Node.js, Go, Rust, tích hợp với Langchain, Llama Index, Crew.ai, Dify, Flowise, Cargo, Zapier, Pipedream,...

Cách sử dụng Firecrawl
1. Dùng API trực tiếp (Cloud version)
Đăng ký tài khoản tại https://firecrawl.dev

Lấy API Key (dùng để xác thực khi gọi API)

Tham khảo các endpoint API:

/scrape: Lấy nội dung một trang

/crawl: Crawl toàn website hoặc các trang con

/map: Lấy toàn bộ link trong website

/search: Tìm kiếm và lấy nội dung từ kết quả tìm kiếm

/extract: Trích xuất dữ liệu có cấu trúc, có thể truyền prompt/schema AI

Ví dụ gọi API bằng curl để crawl:

bash
Sao chép
Chỉnh sửa
curl -X POST https://api.firecrawl.dev/v1/crawl \
  -H 'Authorization: Bearer fc-YOUR_API_KEY' \
  -d '{"url":"https://docs.firecrawl.dev","limit":10}'
Kết quả trả về sẽ có nội dung các trang con ở định dạng markdown, html, metadata,…

2. Dùng SDK cho các ngôn ngữ
Bạn có thể dùng SDK Firecrawl cho Python, Node.js, Go, Rust.
Ví dụ dùng Python SDK:

python
Sao chép
Chỉnh sửa
pip install firecrawl-py
python
Sao chép
Chỉnh sửa
from firecrawl.firecrawl import FirecrawlApp

app = FirecrawlApp(api_key="fc-YOUR_API_KEY")
result = app.scrape_url('https://firecrawl.dev', formats=["markdown", "html"])
print(result)
Tương tự cho Node.js:

js
Sao chép
Chỉnh sửa
npm install @mendable/firecrawl-js
js
Sao chép
Chỉnh sửa
import FirecrawlApp from '@mendable/firecrawl-js';
const app = new FirecrawlApp({apiKey: "fc-YOUR_API_KEY"});
const scrapeResponse = await app.scrapeUrl('https://firecrawl.dev', { formats: ['markdown', 'html'] });
console.log(scrapeResponse);
Firecrawl có gì khác biệt?
Không cần sitemap: Firecrawl tự động tìm và crawl tất cả các trang liên quan mà không cần sitemap.

Tự động xử lý mọi khó khăn khi crawl: Dynamic content, anti-bot, đa dạng định dạng, action, login, batch scrape…

Dễ tích hợp với AI Framework hiện đại: Langchain, Llama Index, CrewAI, Flowise, Dify, Zapier, Cargo, v.v.

Dùng mã nguồn mở hay Cloud?
Firecrawl có bản mã nguồn mở (AGPL-3.0): Bạn có thể tự host (chạy trên máy chủ của bạn), tùy chỉnh, nhưng có thể thiếu một số tính năng nâng cao như cloud.

Firecrawl Cloud (dịch vụ trả phí, nhiều tính năng hơn): Dùng trực tiếp qua API, không cần tự cài đặt, update liên tục, nhiều tính năng AI nâng cao, bảo trì sẵn.

Lưu ý khi sử dụng
Hãy tôn trọng quy định của các website, không scrape nội dung vi phạm chính sách.

Firecrawl tự động tuân thủ robots.txt (không lấy nội dung nếu website cấm).

Bạn chịu trách nhiệm về việc sử dụng dữ liệu lấy được từ các website đó.

Tóm tắt lại cho người mới
Firecrawl = API / SDK giúp bạn lấy sạch nội dung mọi website, chuyển thành dạng markdown, html, structured data, cực kỳ phù hợp cho các ứng dụng AI, data, phân tích, tự động hóa.

Dùng dễ, tài liệu đầy đủ, chỉ cần API Key và vài dòng code là dùng được.

Có thể dùng miễn phí bản mã nguồn mở, hoặc dùng cloud cho tiện lợi.
