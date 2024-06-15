# Use the official Node.js image.
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and yarn.lock
COPY package.json yarn.lock ./

# Install dependencies
RUN yarn install

# Copy the rest of the application code
COPY . .

# Generate Prisma client
RUN npx prisma generate

# Build the NestJS app
RUN yarn build

# Expose the port the app runs on
EXPOSE 5000

# Start the NestJS app
CMD ["yarn", "start:prod"]

