# Unvalidated =_Redirect
Unvalidated redirect is when a web application accepts untrusted input that can cause the web application to redirect to an untrusted URL. By modifying redirect URL input to a malicious site, an attacker may successfully launch a phishing scam and steal user credentials.

## Example
<a href="http://192.168.43.251/">Index</a> present such a vulnerablity. When inspecting th footer elements. We see that the elements are respectively linked to redirects that we can manipulate.

## Exploit
When we manilate these values and click them, we are presented with our flag: b9e775a0291fed784a2d9680fcfad7edd6b8cdf87648da647aaf4bba288bcab3

## Remedy
*  validate and sanitise user-input to determine whether the URL is safe.

## Resources
* https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html