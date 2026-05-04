# Embedded Signup with Next.js

## Frontend Component
```tsx
export const WhatsAppConnectButton = () => {
  const handleConnect = () => {
    FB.login((res) => {
      if (res.authResponse) {
        const { code } = res.authResponse;
        fetch('/api/whatsapp/exchange-token', {
          method: 'POST',
          body: JSON.stringify({ code })
        });
      }
    }, { config_id: 'YOUR_CONFIG_ID', response_type: 'code' });
  };
  return <button onClick={handleConnect}>Connect WhatsApp</button>;
};
```

## API Route (Next.js)
```ts
export async function POST(req: Request) {
  const { code } = await req.json();
  const res = await fetch(`https://graph.facebook.com/v20.0/oauth/access_token?code=${code}&client_id=${APP_ID}&client_secret=${APP_SECRET}`);
  const data = await res.json();
  // Save to Supabase
}
```
