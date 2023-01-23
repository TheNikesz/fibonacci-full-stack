## CZĘŚĆ OBOWIĄZKOWA

Okno aplikacji zawierające interfejs kalkulatora:

![Obowiazkowa_1.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Obowiazkowa_1.png)

Okno aplikacji zawierające dane studenta:

![Obowiazkowa_2.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Obowiazkowa_2.png)

Wynik działania polecenia ```aws elasticbeanstalk describe-environments --environment-names multifib-env --output json```:

![Obowiazkowa_3.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Obowiazkowa_3.png)

## CZĘŚĆ DODATKOWA

# Zadanie 2

# 1.

Wynik działania polecenia ```aws ec2 describe-instances --instance-ids i-0515311a6f131b461 --output json```:

![Dodatkowa_2_1.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Dodatkowa_2_1.png)

Wynik działania polecenia ```aws ec2 describe-vpcs --vpc-ids vpc-0f7a16648e735060f --output json```:

![Dodatkowa_2_2.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Dodatkowa_2_2.png)

Wynik działania polecenia ```aws iam get-user --user-name github-action --output json```:

![Dodatkowa_2_3.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Dodatkowa_2_3.png)

Wynik działania polecenia ```aws rds describe-db-instances --db-instance-identifier multifib-postgres --output json```:

![Dodatkowa_2_4.png](https://github.com/TheNikesz/fibonacci-full-stack/blob/main/Screens/Dodatkowa_2_4.png)

# 2.

W celu wykonania zadania kierowałem się następującym poradnikiem: [GitHub Actions Deploy by Git Tag to AWS Elastic Beanstalk](https://gist.github.com/noinarisak/c665f18bdd343880ab2e49253d085b0c)


W ```inputs``` w ```workflow_dispatch``` można zdefiniować wartości pobierane od użytkownika przy uruchomianiu GA Workflow. W tym przypadku tag oraz nazwa aplikacji. Dotyczyąca tego dokumentacja: [GitHub Actions: Input types for manual workflows](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#onworkflow_dispatchinputs)

Jobs o nazwach ```Checkout source code``` i ```Checkout version tag``` umożliwiają worklfow dostęp do kodu, jak i tagu.

```version_label``` i ```version_description``` w job o nazwie ```Deploy to EB``` (wykorzystującym [GitHub Action Beanstalk Deploy](https://github.com/marketplace/actions/beanstalk-deploy)) zostaną automatycznie ustawione odpowiednio na tag i SHA commitu.