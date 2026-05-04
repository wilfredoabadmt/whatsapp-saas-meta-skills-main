# WhatsApp SaaS Implementation Plan

Following the `whatsapp-saas-meta-infra` skill guidelines.

## Phase 1: Meta App Setup
- Create Meta App (Business type)
- Configure WhatsApp product
- Set up Embedded Signup config

## Phase 2: Embedded Signup
- Implement frontend launcher
- Handle OAuth callback
- Send `code` to backend

## Phase 3: Token Exchange
- POST /api/whatsapp/exchange-token
- Meta Graph API call to exchange code for token
- Save to Supabase

## Phase 4: Supabase Schema
```sql
create table whatsapp_connections (
  id uuid primary key default uuid_generate_v4(),
  user_id uuid references auth.users(id),
  waba_id text not null,
  phone_number_id text not null,
  access_token text not null,
  is_active boolean default true
);
```

## Phase 5: Webhooks
- Verification (GET)
- Ingestion (POST)
- Upsert by message_id
