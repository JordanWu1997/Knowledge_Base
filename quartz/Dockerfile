FROM node:22-alpine

# Install git (required by Quartz for tracking page modifications)
RUN apk add --no-cache git coreutils

WORKDIR /quartz

# Clone official Quartz v4 repository
RUN git clone --depth 1 https://github.com/jackyzha0/quartz.git .

# Install dependencies
RUN npm ci

# Create empty content directory placeholder
RUN mkdir -p /quartz/content

EXPOSE 8088

CMD ["npx", "quartz", "build", "--serve", "--port", "8088"]
