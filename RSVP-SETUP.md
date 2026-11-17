# Connect the wedding RSVP to Google Sheets

1. Open the **private RSVP Google Sheet already created for this wedding**: https://docs.google.com/spreadsheets/d/1ugvv4WAV1cPP8UOJaRKy3ldEYRvG3w1RADw24Uq2qMI/edit . It already has an `RSVP Responses` tab with column headers. Do not create another sheet.
2. Open **Extensions → Apps Script**, replace the starter code with the contents of `google-apps-script-rsvp.gs`, and save.
3. Select **Deploy → New deployment → Web app**. Set **Execute as: Me** and **Who has access: Anyone** (guest submissions must work without a Google login). Authorize the script under your Google account. Do **not** make the spreadsheet itself public.
4. Copy the deployment URL ending in `/exec`. In `index.html`, replace `const RSVP_ENDPOINT='';` with `const RSVP_ENDPOINT='https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec';`.
5. Publish the site, submit a test RSVP and **verify the new row exists in the private Sheet** before sending invitations. Also test from a phone and with Hindi selected.

**Important:** Browser cross-origin restrictions mean the website uses a `no-cors` POST. It cannot read the Apps Script response, so the website says the response was *sent*, not verified as stored. Check the Sheet after a test. Do not treat a browser send as proof of receipt. Do not put a Google Sheet edit URL or API key in public website code.

The previous Veena audio track and the new Sajdaa audio track are both retained in the repo.
