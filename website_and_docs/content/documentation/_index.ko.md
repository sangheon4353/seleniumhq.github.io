---
title: "Selenium 브라우저 자동화 프로젝트"
linkTitle: "문서"
cascade:
- type: docs
aliases: ["/documentation/ko/"]
---

Selenium은 웹 브라우저의 자동화를 지원하고 지원하는 다양한 도구와 라이브러리를 위한 우산 프로젝트입니다.

Selenium은 브라우저와의 사용자 상호작용을 에뮬레이트하기 위한 확장, 브라우저 할당을 확장하기 위한 배포 서버, 그리고 당신이 모든 주요 웹 브라우저에 대해 호환 가능한 코드를 작성할 수 있게 해주는 W3C 웹드라이버 규격의 구현을 위한 인프라를 제공합니다.

이 프로젝트는 수천 시간의 시간을 들여 자원 봉사자들이 만들고, 누구나 자유롭게 소스 코드를 사용하고, 즐기고, 개선할 수 있게 만들었습니다.

Selenium은 브라우저 공급업체, 엔지니어 및 마니아를 함께 모아 웹 플랫폼의 자동화에 대한 공개 토론을 진행하고, 그 프로젝트는 지역사회를 가르치고 육성하기 위해 연례 회의를 조직합니다.

Selenium의 핵심에는 웹드라이버가 있는데, 웹드라이버는 많은 브라우저에서 서로 교환하여 실행할 수 있는 명령어 집합을 작성하기 위한 인터페이스다. 다음은 가장 간단한 지시사항 중 하나입니다.


{{< tabpane langEqualsHeader=true >}}
  {{< tab header="Java" >}}
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.WebDriverWait;
import static org.openqa.selenium.support.ui.ExpectedConditions.presenceOfElementLocated;
import java.time.Duration;

public class HelloSelenium {

    public static void main(String[] args) {
        WebDriver driver = new FirefoxDriver();
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
        try {
            driver.get("https://google.com/ncr");
            driver.findElement(By.name("q")).sendKeys("cheese" + Keys.ENTER);
            WebElement firstResult = wait.until(presenceOfElementLocated(By.cssSelector("h3")));
            System.out.println(firstResult.getAttribute("textContent"));
        } finally {
            driver.quit();
        }
    }
}
  {{< /tab >}}
  {{< tab header="Python" >}}
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support.expected_conditions import presence_of_element_located

#This example requires Selenium WebDriver 3.13 or newer
with webdriver.Firefox() as driver:
    wait = WebDriverWait(driver, 10)
    driver.get("https://google.com/ncr")
    driver.find_element(By.NAME, "q").send_keys("cheese" + Keys.RETURN)
    first_result = wait.until(presence_of_element_located((By.CSS_SELECTOR, "h3")))
    print(first_result.get_attribute("textContent"))
  {{< /tab >}}
  {{< tab header="CSharp" >}}
using System;
using OpenQA.Selenium;
using OpenQA.Selenium.Firefox;
using OpenQA.Selenium.Support.UI;

class HelloSelenium {
  static void Main() {
    using(IWebDriver driver = new FirefoxDriver()) {
      WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(10));
      driver.Navigate().GoToUrl("https://www.google.com/ncr");
      driver.FindElement(By.Name("q")).SendKeys("cheese" + Keys.Enter);
      wait.Until(webDriver => webDriver.FindElement(By.CssSelector("h3")).Displayed);
      IWebElement firstResult = driver.FindElement(By.CssSelector("h3"));
      Console.WriteLine(firstResult.GetAttribute("textContent"));
    }
  }
}
  {{< /tab >}}
  {{< tab header="Ruby" >}}
require 'selenium-webdriver'

driver = Selenium::WebDriver.for :firefox
wait = Selenium::WebDriver::Wait.new(timeout: 10)

begin
  driver.get 'https://google.com/ncr'
  driver.find_element(name: 'q').send_keys 'cheese', :return
  first_result = wait.until { driver.find_element(css: 'h3') }
  puts first_result.attribute('textContent')
ensure
  driver.quit
end
  {{< /tab >}}
  {{< tab header="JavaScript" >}}
const {Builder, By, Key, until} = require('selenium-webdriver');

(async function example() {
    let driver = await new Builder().forBrowser('firefox').build();
    try {
        // Navigate to Url
        await driver.get('https://www.google.com');

        // Enter text "cheese" and perform keyboard action "Enter"
        await driver.findElement(By.name('q')).sendKeys('cheese', Key.ENTER);

        let firstResult = await driver.wait(until.elementLocated(By.css('h3')), 10000);

        console.log(await firstResult.getAttribute('textContent'));
    }
    finally{
        await driver.quit();
    }
})();
  {{< /tab >}}
  {{< tab header="Kotlin" >}}
import org.openqa.selenium.By
import org.openqa.selenium.Keys
import org.openqa.selenium.firefox.FirefoxDriver
import org.openqa.selenium.support.ui.ExpectedConditions.presenceOfElementLocated
import org.openqa.selenium.support.ui.WebDriverWait
import java.time.Duration

fun main() {
    val driver = FirefoxDriver()
    val wait = WebDriverWait(driver, Duration.ofSeconds(10))
    try {
        driver.get("https://google.com/ncr")
        driver.findElement(By.name("q")).sendKeys("cheese" + Keys.ENTER)
        val firstResult = wait.until(presenceOfElementLocated(By.cssSelector("h3")))
        println(firstResult.getAttribute("textContent"))
    } finally {
        driver.quit()
    }
}
  {{< /tab >}}
{{< /tabpane >}}



다양한 프로젝트 구성 요소를 확인하고 Selenium이 적합한 도구인지 결정하려면 [개요]({{< ref "/overview.md" >}})를 참조하십시오.

[시작 단계]({{< ref "/getting_started.md" >}})로 이동하여 Selenium을 설치하고 테스트 자동화 도구로 성공적으로 사용할 수 있는 방법을 이해하고 이와 같은 간단한 테스트를 여러 다른 운영 체제에서 여러 브라우저의 분산 환경에서 실행할 수 있도록 확장해야 합니다.
