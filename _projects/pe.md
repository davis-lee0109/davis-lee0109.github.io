---
title: 锻炼打卡
---

每日锻炼打卡

<table border="1">
  <tr>
    <th>日期</th>
    <th>内容</th>
    <th>数量</th>
  </tr>
  {% for item_i in site.data.pe_record %}
  <tr>
    <td>{{ item_i.date }}</td>
    <td>{{ item_i.item }}</td>
    <td>{{ item_i.value }}</td>
  </tr>
  {% endfor %}
</table>

血压记录

<table border="1">
  <tr>
    <th>日期</th>
    <th>收缩压</th>
    <th>舒张压</th>
    <th>心率</th>
  </tr>
  {% for item_i in site.data.blood_pressure_record %}
  <tr>
    <td>{{ item_i.date }}</td>
    <td>{{ item_i.SBP }}</td>
    <td>{{ item_i.DBP }}</td>
    <td>{{ item_i.HR }}</td>
  </tr>
  {% endfor %}
</table>