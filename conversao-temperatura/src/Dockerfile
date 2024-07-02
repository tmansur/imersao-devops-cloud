# Imagem base para criação da imagem do projeto
FROM node:22.0.0
# Diretório de trabalho onde os arquivos do projeto serão inseridos
WORKDIR /app
# Copia as dependência do projeto local para o diretório corrente dentro da imagem
COPY package*.json ./
# Executa o npm para baixar as dependências
RUN npm install
# Faz a cópia dos outros arquivos do projeto local para dentro da imagem
COPY . .
# Define na imagem a porta que será exposta no container
EXPOSE 8080
# Comando de start do container. Sempre que o container for inicializado esse comando é executado
CMD ["node", "server.js"]
