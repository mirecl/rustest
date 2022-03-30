<a href="https://pepy.tech/project/pprof"><img src="https://pepy.tech/badge/pprof?kill_cache=1"/></a>
<img src="https://pepy.tech/badge/pprof"/>

<img src="https://img.shields.io/github/license/mirecl/pprof"/>
<img src="https://img.shields.io/github/license/mirecl/pprof?kill_cache=1"/>

### Версии:
Python - **3.6.15**:
+ xmltodict - **0.12.0**
+ lxml - **4.7.1**

Rust - **1.57.0** 
+ pyo3 - **0.15.1**
+ quick-xml - **0.22.0**
+ serde - **1.0.136**

**Структура XML-файла:**
```xml
<data>
  <person>
    <address>8450 Reid Orchard Apt. 815</address>
    <age>76</age>
    <amount>45826</amount>
    <city>East Linda</city>
    <country>IS</country>
    <credit_card_number>4926698773041235</credit_card_number>
    <currency>ZWD</currency>
    <date>1993-07-22</date>
    <email>ulambert@alvarez-carpenter.org</email>
    <job>Personal assistant</job>
    <male>False</male>
    <name>Daniel Pennington</name>
    <phone_number>6641446731</phone_number>
    <postcode>55819</postcode>
    <quantity>1222</quantity>
    <site>web-60.campbell.info</site>
  </person>
  <person>
     ...
  </person>
<data>
```
**Результат преобразования в Python-объект:**
```python
[
  {
     'name': 'Daniel Pennington',
     'city': 'East Linda',
     'address': '8450 Reid Orchard Apt. 815',
     'email': 'ulambert@alvarez-carpenter.org',
     'country': 'IS',
     'credit_card_number': 4926698773041235,
     'currency': 'ZWD',
     'site': 'web-60.campbell.info',
     'job': 'Personal assistant',
     'postcode': 55819,
     'phone_number': '6641446731',
     'male': False,
     'amount': 45826,
     'quantity': 1222,
     'age': 76,
     'date': '1993-07-22'
  },
  {
   ...
  }
]
```

<table>
    <caption>Время преобразования XML-файла в Python-объект в зависимости от размера XML.</caption>
    <thead>
        <tr>
            <th>Library</th>
            <th>Language</th>
            <th>60Kb</th>
            <th>120Kb</th>
            <th>300Kb</th>
            <th>600Kb</th>
            <th>1.2Mb</th>
            <th>3.2Mb</th>
            <th>9Mb</th>
            <th>30Mb</th>
            <th>60Mb</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>xmltodict</td>
            <td>Python</td>
            <td>99.4ms</td>
            <td>104.1ms</td>
            <td>144.0ms</td>
            <td>194.3 ms</td>
            <td>311.9ms</td>
            <td>679.2ms</td>
            <td>1809.6s</td>
            <td>6.040s</td>
            <td>11.817s</td>
        </tr>
        <tr>
            <td>lxml</td>
            <td>Cython</td>
            <td>56.8ms</td>
            <td>58.8ms</td>
            <td>70.7ms</td>
            <td>86.1ms</td>
            <td>123.1ms</td>
            <td>235.5ms</td>
            <td>615.1ms</td>
            <td>1.815s</td>
            <td>3.529s</td>
        </tr>
        <tr>
            <td>pyo3+quick-xml</td>
            <td>Rust</td>
            <td style="color:green">36.4ms</td>
            <td style="color:green">37.5ms</td>
            <td style="color:green">51.4ms</td>
            <td style="color:green">55.4ms</td>
            <td style="color:green">79.9ms</td>
            <td style="color:green">149.9ms</td>
            <td style="color:green">365.7ms</td>
            <td style="color:green">1.161s</td>
            <td style="color:green">2.304s</td>
        </tr>
    </tbody>
</table>


