# Results System — Android WebView

Mradi huu huunda Android app ya WebView kwa website `https://results.siwitisoftware.com/`.

- App name: Results System
- Package ID: `com.siwitisoftware.results.twa`
- Zoom controls: zimezimwa
- JavaScript/DOM storage: zimewezeshwa kwa mfumo wa website
- Downloads: hutumwa kwenye Downloads ya kifaa
- Back button: hurudi ukurasa uliotangulia
- Build: GitHub Actions (hakuna kompyuta inayohitajika ikiwa unatumia GitHub kwenye simu)

## Kuweka mradi wote mara moja kwenye GitHub

1. Pakua ZIP hii na uifungue (extract).
2. Fungua repository ya GitHub unayotaka kutumia.
3. Ikiwa repository tayari ina mafaili, tengeneza repository mpya au hakikisha hutafuta mafaili muhimu kwa kuyabadilisha.
4. Kwenye ukurasa wa repository, chagua **Add file → Upload files**.
5. Pakia mafaili yote na folda zilizomo ndani ya folda hii, ikiwemo `.github/workflows/android-build.yml`. Usipakie ZIP kama faili moja tu.
6. Bonyeza **Commit changes**. GitHub Actions itaanza build yenyewe; unaweza pia kwenda **Actions → Build Results System WebView → Run workflow**.

## Signing key ya app ya sasa

Usiweke `signing.keystore`, nywila zake, au taarifa za siri ndani ya repository. Weka kwenye **Settings → Secrets and variables → Actions → New repository secret**:

- `ANDROID_KEYSTORE_BASE64`: maudhui ya faili la keystore lililogeuzwa kuwa Base64
- `ANDROID_KEYSTORE_PASSWORD`: nywila ya keystore
- `ANDROID_KEY_ALIAS`: alias ya cheti
- `ANDROID_KEY_PASSWORD`: nywila ya key

Hifadhi keystore yako ya awali kwa usalama. Usitumie keystore hii kwa repository ya umma. Ikiwa unatumia simu pekee, unaweza kuhitaji app/terminal inayoweza kugeuza faili kuwa Base64; usitume nywila hapa kwenye mazungumzo.

## Kupakua build

Baada ya workflow kukamilika, fungua run iliyofanikiwa, kisha sehemu ya **Artifacts** pakua `Results-System-WebView-Android`. APK ya debug ni ya majaribio tu. APK/AAB ya release inaweza kusainiwa tu ikiwa secrets zote zimewekwa. Kabla ya kusambaza, jaribu login, data, PDF, download na matumizi bila mtandao.

## Muhimu kuhusu offline

Hii ni WebView wrapper ya website iliyopo, si mfumo uliogeuzwa wote kuwa native/offline. Uwezo wa offline unategemea service worker, cache na hifadhi ya website; lazima ujaribiwe kwenye WebView kwa sababu data ya Chrome/TWA haimaanishi itahamia moja kwa moja kwenye WebView. PDF inaweza kupakuliwa, lakini kuonyesha PDF ndani ya app kunategemea jinsi website inavyotoa PDF na programu za kifaa.
