FROM oven/bun:1
WORKDIR /app

# Copy root package files
COPY package.json bun.lock ./

# Copy all packages and apps
COPY . .

# Install dependencies for the monorepo
RUN bun install

# Switch to the api-backend directory
WORKDIR /app/apps/api-backend

# Expose the API port (assuming 3000, adjust if needed)
EXPOSE 3000

# Start the application
CMD ["bun", "run", "src/index.ts"]
