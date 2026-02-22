FROM oven/bun:1
WORKDIR /app

# Copy root package files
COPY package.json bun.lock ./

# Copy all packages and apps
COPY . .

# Install dependencies for the monorepo
RUN bun install

# Switch to the primary-backend directory
WORKDIR /app/apps/primary-backend

# Expose the API port (assuming 3002, adjust if needed)
EXPOSE 3002

# Start the application
CMD ["bun", "run", "src/index.ts"]
