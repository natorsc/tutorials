services:
  uptime-kuma:
    image: louislam/uptime-kuma:1
    container_name: uptime-kuma
    restart: unless-stopped
    ports:
      - "3001:3001"
    volumes:
      # Mantendo o bind mount para facilitar a sua cópia manual de dados
      # O './' indica que a pasta será criada no mesmo local do arquivo yaml
      - ./data:/app/data
    environment:
      - TZ=America/Sao_Paulo
      - UMASK=0022
    networks:
      - kuma_network
    healthcheck:
      test: ["CMD", "curl", "-f", "http://0.0.0.0:3001"]
      interval: 30s
      retries: 3
      start_period: 20s
      timeout: 10s
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"

networks:
  kuma_network:
    driver: bridge
