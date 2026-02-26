# 📘 Guide Complet sur Cucumber

## 🌱 Introduction

Cucumber est un outil de test BDD (Behavior Driven Development) qui permet d'écrire des tests sous une forme compréhensible en langage naturel grâce à Gherkin.

🔹 BDD signifie Behavior-Driven Development ou en français : Développement piloté par le comportement.

C’est une méthodologie de test logiciel qui vise à rapprocher développeurs, testeurs et parties prenantes (product owners, clients) autour du comportement attendu d’une application plutôt que de détails techniques.

🔹 Gherkin est un langage structuré utilisé en BDD (Behavior-Driven Development) pour écrire des scénarios de tests lisibles par les humains.


## 🔧 Installation

Prérequis
Java (JDK 8 ou supérieur)
Maven ou Gradle


Installation via Maven
Ajoutez ces dépendances dans votre pom.xml :
```xml
<dependencies>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-java</artifactId>
        <version>7.0.0</version>
    </dependency>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-junit</artifactId>
        <version>7.0.0</version>
</dependencies>
````
## 📝 Syntaxe Gherkin

Les scénarios de test sont écrits dans des fichiers .feature avec la syntaxe Gherkin.

Exemple :
```` Gherkin
Feature: Connexion utilisateur
  Scenario: Connexion réussie
    Given L'utilisateur est sur la page de connexion
    When Il saisit un identifiant valide
    And Il saisit un mot de passe valide
    Then Il est redirigé vers la page d'accueil
`````
## 🚀 Implémentation en Java
Chaque étape (Given, When, Then) doit être liée à une méthode Java dans une classe de définition de step.
```` java
import io.cucumber.java.en.*;

public class LoginSteps {
    @Given("L'utilisateur est sur la page de connexion")
    public void userIsOnLoginPage() {
        System.out.println("Utilisateur sur la page de connexion");
    }

    @When("Il saisit un identifiant valide")
    public void enterValidUsername() {
        System.out.println("Saisie de l'identifiant valide");
    }

    @When("Il saisit un mot de passe valide")
    public void enterValidPassword() {
        System.out.println("Saisie du mot de passe valide");
    }

    @Then("Il est redirigé vers la page d'accueil")
    public void redirectedToHomepage() {
        System.out.println("Redirection vers la page d'accueil");
    }
}

##🏗️ Exécution des Tests
``` JUnit
Créer une classe de test runner avec JUnit :

import org.junit.runner.RunWith;
import io.cucumber.junit.Cucumber;
import io.cucumber.junit.CucumberOptions;

@RunWith(Cucumber.class)
@CucumberOptions(features = "src/test/resources/features", glue = "stepDefinitions")
public class TestRunner {
}
Exécutez avec Maven :
``` Maven
mvn test

## 🎯 Avantages de Cucumber
✅ Lisible par les non-développeurs ✅ Facilite la collaboration entre équipes ✅ Tests réutilisables et modulables
Cucumber simplifie l'automatisation des tests et améliore la communication entre les équipes .
## 📚 Ressources
Documentation Officielle
Exemples et Tutoriels

# MERCI POUR VOTRE ATTENTION

        <scope>test</scope>
    </dependency>
</dependencies>
