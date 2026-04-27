# Vibe Chat — Cómo ejecutar localmente en tu PC

## Requisitos
- Node.js 20 o superior — https://nodejs.org
- pnpm — instálalo con: `npm install -g pnpm`
- PostgreSQL (local o remoto) — opcional si solo quieres ver el código

## Pasos
1. Descomprime el archivo .zip
2. Abre una terminal en la carpeta `vibe-chat`
3. Instala dependencias:
   ```
   pnpm install
   ```
4. Configura tus claves de OpenAI en un archivo `.env` en la raíz:
   ```
   AI_INTEGRATIONS_OPENAI_BASE_URL=https://api.openai.com/v1
   AI_INTEGRATIONS_OPENAI_API_KEY=sk-tu-clave-aqui
   DATABASE_URL=postgres://usuario:contraseña@localhost:5432/vibe_chat
   PORT=8080
   BASE_PATH=/
   ```
5. Crea las tablas:
   ```
   pnpm --filter @workspace/db run push
   ```
6. Arranca el backend:
   ```
   pnpm --filter @workspace/api-server run dev
   ```
7. En otra terminal, arranca el frontend:
   ```
   PORT=5173 BASE_PATH=/ pnpm --filter @workspace/ai-chat run dev
   ```
8. Abre http://localhost:5173

Hecho con cariño por warIACreator.
