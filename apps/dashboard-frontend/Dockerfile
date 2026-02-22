FROM oven/bun:1
WORKDIR /app

# Copy root package files
COPY package.json bun.lock ./

# Copy all packages and apps
COPY . .

# Install dependencies for the monorepo
RUN bun install

# Switch to the dashboard-frontend directory
WORKDIR /app/apps/dashboard-frontend

# Build the frontend if needed (optional depending on whether src/index.ts serves dynamic or static)
RUN bun run build

# Expose the frontend port (typically 3001)
EXPOSE 3001

# Start the application using the start script
CMD ["bun", "run", "start"]
