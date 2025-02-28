---
title: Hinzufügen eines Mitarbeiters zu einem Repository-Sicherheitshinweis
intro: Du kannst andere Benutzer oder Teams hinzufügen, damit sie mit Dir an einem Sicherheitshinweis zusammenarbeiten.
redirect_from:
- /articles/adding-a-collaborator-to-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/adding-a-collaborator-to-a-maintainer-security-advisory
- /github/managing-security-vulnerabilities/adding-a-collaborator-to-a-security-advisory
- /code-security/security-advisories/adding-a-collaborator-to-a-security-advisory
versions:
  fpt: '*'
  ghec: '*'
type: how_to
topics:
- Security advisories
- Vulnerabilities
- Collaboration
shortTitle: Add collaborators
ms.openlocfilehash: 6fa4062fab8e4ffc59724ceb0ba3b6b536871df9
ms.sourcegitcommit: fcf3546b7cc208155fb8acdf68b81be28afc3d2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "147879139"
---
Personen mit Administratorberechtigungen für einen Sicherheitshinweis können Mitarbeiter zu Sicherheitshinweisen hinzufügen.

{% data reusables.security-advisory.repository-level-advisory-note %}

## Einen Mitarbeiter zu einem Sicherheitshinweis hinzufügen

Mitarbeiter haben Schreibberechtigungen für den Sicherheitshinweis. Weitere Informationen findest Du unter „[Berechtigungsstufen für Repository-Sicherheitshinweise](/code-security/repository-security-advisories/permission-levels-for-repository-security-advisories).“

{% note %}

{% data reusables.repositories.security-advisory-collaborators-public-repositories %} Weitere Informationen zum Entfernen eines Mitarbeiters aus einem Sicherheitshinweis findest Du unter „[Entfernen eines Mitarbeiters aus einem Repository-Sicherheitshinweis](/code-security/repository-security-advisories/removing-a-collaborator-from-a-repository-security-advisory).“

{% endnote %}

{% data reusables.repositories.navigate-to-repo %} {% data reusables.repositories.sidebar-security %} {% data reusables.repositories.sidebar-advisories %}
4. Klicke in der Liste „Security Advisories“ (Sicherheitshinweise) auf den Hinweis, zu dem Du einen Mitarbeiter hinzufügen möchtest.
5. Gib auf der rechten Seite unter "Collaborators" (Mitarbeiter) den Namen des Benutzers oder Teams ein, das Du dem Sicherheitshinweis hinzufügen möchtest.
  ![Feld zum Eingeben von Benutzer- oder Teamnamen](/assets/images/help/security/add-collaborator-field.png)
6. Klicken Sie auf **Hinzufügen**.
  ![Schaltfläche „Hinzufügen“](/assets/images/help/security/security-advisory-add-collaborator-button.png)

## Weiterführende Themen

- „[Berechtigungsstufen für Repository-Sicherheitshinweise](/code-security/repository-security-advisories/permission-levels-for-repository-security-advisories)“
- „[Zusammenarbeit in einem temporären privaten Fork, um eine Sicherheitslücke im Repository zu beheben](/code-security/repository-security-advisories/collaborating-in-a-temporary-private-fork-to-resolve-a-repository-security-vulnerability)“
- „[Einen Mitarbeiter aus einem Repository-Sicherheitshinweis entfernen](/code-security/repository-security-advisories/removing-a-collaborator-from-a-repository-security-advisory).“
