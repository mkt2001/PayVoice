# Payvoice (starter project)

## GitHub से APK बनाने के चरण
1. GitHub पर नया repository बनाएं, जैसे `Payvoice`.
2. इस ZIP को extract करके अंदर की सभी files और folders repository के root में upload करें (ZIP को सिर्फ एक file के रूप में upload न करें).
3. Commit changes करें और repository के Actions tab में `Build Payvoice APK` workflow खोलें.
4. `Run workflow` दबाएं (या main branch पर push के बाद workflow अपने आप चलेगा).
5. Workflow सफल होने पर run के नीचे `Payvoice-debug-apk` artifact डाउनलोड करें और ZIP extract करके `app-debug.apk` लें.
6. फोन पर APK install करें. App खोलकर अपना message और speed सेट करें, Save दबाएं, फिर Notification Access खोलकर Payvoice को अनुमति दें.
7. Paytm/Google Pay/PhonePe की notifications चालू रखें. पहले छोटे टेस्ट पेमेंट/टेस्ट नोटिफिकेशन से जांचें.

## Message template
`{app}` = Paytm / Google Pay / PhonePe / UPI ऐप
`{amount}` = notification से निकाली गई रकम

Example: `{app} पर {amount} प्राप्त हुए। धन्यवाद!`

## Important limitations
- यह starter code केवल चुने हुए payment apps के notifications पढ़ता है; ऐप/OS update से package IDs या notification format बदल सकते हैं.
- Notification में payment-जैसा text होना बैंक में वास्तविक रकम जमा होने का प्रमाण नहीं है. इसे financial verification के लिए इस्तेमाल न करें.
- Hindi voice और accent आपके Android TTS engine/installed voices पर निर्भर हैं. Settings में Google Speech Services में Hindi voice install करें.
- यह शुरुआती project है; production release से पहले Android Studio में build/test, notification parsing, privacy policy और security review करें.
