# Exemple d'application IBM Security Verify pour Passkey sur iOS

Une implémentation d'Apple Passkeys avec IBM Security Verify en tant que service FIDO de la partie dépendante.

## Mise en route

Les liens de ressources dans les conditions préalables expliquent et démontrent comment créer une nouvelle application locataire et configurer les paramètres de sécurité pour permettre l'utilisation de FIDO dans l'application d'exemple.

### Prérequis

- Mise en route

> Voir [Avant de commencer](https://github.com/ibm-security-verify/webauthn-relying-party-server-swift/blob/main/README.md)

## Mise en route
1. Ouvrez Terminal et clonez le dépôt et ouvrez le fichier de projet dans Xcode.
   ```
   git clone https://github.com/ibm-security-verify/webauthn-passkey-sample-ios.git
   xed .
   ```

2. Dans le projet **Signing & Capabilities**, mettez à jour les paramètres suivants pour les adapter à votre environnement de développement :
   - Identificateur de bundle
   - Profil de mise à disposition
   - Domaines associés


   La valeur du domaine associé contient l'identifiant de la partie répondante généré par votre locataire IBM Security Verify (ISV) ou votre configuration IBM Security Verify Access (ISVA) sur site.  Par exemple : `webcredentials:example.com`

   Assurez-vous qu'un fichier `apple-app-site-association` (AASA) est présent sur votre domaine dans le répertoire .well-known, et qu'il contient une entrée pour l' App ID de cette application pour le service webcredentials.  Par exemple :
   ```
   "webcredentials": {
      "apps": [ "TEAM.com.company.app" ]
   }
   ```
3. Ouvrir le fichier **PasskeyApp.swift**
4. Remplacer la variable **relyingParty** par le nom d'hôte de la partie se fiant à l'information.  Exemple : `example.com`.


## Ressources
[Prise en charge de l'authentification des clés de sécurité à l'aide de clés physiques](https://developer.apple.com/documentation/authenticationservices/public-private_key_authentication/supporting_security_key_authentication_using_physical_keys)

[Authentification par clé publique-privée](https://developer.apple.com/documentation/authenticationservices/public-private_key_authentication)

[Authentification Web du W3C](https://www.w3.org/TR/webauthn-2/)

<!-- v2.3.7 : caits-prod-app-gp_webui_20241231T141211-7_en_fr -->