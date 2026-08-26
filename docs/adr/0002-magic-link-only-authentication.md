# Magic-link-only authentication

Status: accepted

Users authenticate via Supabase's email Magic Link / OTP flow only; the app never collects or stores a password. We considered offering traditional email+password (or both alongside magic link), but passwordless authentication minimizes the personal data the app has to protect and disclose on its GDPR/privacy page, and avoids building password-reset, password-strength, and credential-breach handling altogether.
