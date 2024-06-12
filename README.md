# Solution
## Task (1): Làm quen với Generative AI model
**Cài đặt Ollama**
Sau khi tải và chạy Ollama Installer thành công. Chạy lệnh ```ollama run phi``` lần đầu để pull model về và thực hiện lại câu lệnh để promt model.
![Promting ollama](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/8a7fed85-b771-4c69-8ec7-95dfd0a69406)
## Task (2): Làm quen với Docker & Docker Compose
- Cài đặt docker.
- Clone open-webui từ github về
```git clone https://github.com/open-webui/open-webui.git```
- Vào thư mục **open-webui** sẽ có sẵn file **docker-compose.yaml** với 2 service là ***ollama*** và ***open-webui***. Chạy file này bằng lệnh ```docker-compose up```. Lúc này đã có thể truy cập trang web nhưng sẽ không có model.
![Add 2 containers](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/5ac441b0-f3d9-49e1-ac7e-54a28d8cc08d)
- Để pull model phi về ollama container, thực hiện câu lệnh sau
```
docker exec -it ollama /bin/bash
ollama pull phi
```
- Vào ```localhost:3000``` để test.

![Promting on web-ui](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/9668422b-56b0-4567-8c94-34f13c93f737)
## Task (3): Làm quen với GCP Agent Builder
Chưa thực hiện được do không có thẻ visa.
## Task (4): Tìm hiểu cách RAG hoạt động
- Thêm service ***weaviate*** vào **docker-compose.yaml** rồi chạy lại lệnh ```docker-compose up```
![Add service weaviate](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/6bcc5156-34ec-4565-b4cc-2880a4c8b752)
- Tiến hành pull model nomic-embed-text về
```
docker exec -it ollama /bin/bash
ollama pull nomic-embed-text
```
- Viết code python để tạo schema, thêm một số record, tiến hành query nearText, singlePrompt và groupedTask (xem trong file ***rag-with-ollama-weaviate.ipynb***)
- Hình ảnh sau khi tạo schema
![Schema view](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/0963ff46-f6e2-46c1-a247-0467c9204189)
- Các record
![Records](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/8af5b4e1-b04d-42d8-8e82-7d0926f95573)
- Kết quả cho query nearText
![nearText](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/93fad471-4bb9-442b-829d-e57256e70645)
- Kết quả cho query singlePrompt
![singlePrompt](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/09289da4-914f-48dd-b177-3e8222217e36)
- Kết quả cho query groupedTask
![groupedTask](https://github.com/DTK1710/rag-with-ollama-weaviate-solution/assets/119122261/e900f2a0-1cd9-4915-991a-54293866a13d)
