# Webhook Debugging and Ingestion

## GET Verification
```ts
if (mode === 'subscribe' && token === VERIFY_TOKEN) {
  return new Response(challenge);
}
```

## POST Ingestion
```ts
const body = await req.json();
const entry = body.entry?.[0];
const changes = entry?.changes?.[0]?.value;

if (changes?.statuses) {
  for (const status of changes.statuses) {
    await supabase.from('whatsapp_message_events').upsert({
      message_id: status.id,
      status: status.status
    }, { onConflict: 'message_id' });
  }
}
```
