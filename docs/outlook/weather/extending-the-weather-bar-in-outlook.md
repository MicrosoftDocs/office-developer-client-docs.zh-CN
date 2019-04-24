---
title: 扩展 Outlook 中的天气栏
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3b355b98-dd7d-4f16-8257-367e5dd61b34
description: 了解在 Outlook 2013 中如何在天气栏中插入第三方天气 Web 服务，以提供用户所选位置的天气状况。
ms.openlocfilehash: 0423e149306bf7562dd525f1b7460a63cbace372
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336565"
---
# <a name="extending-the-weather-bar-in-outlook"></a>扩展 Outlook 中的天气栏

了解在 Outlook 2013 中如何在天气栏中插入第三方天气 Web 服务，以提供用户所选位置的天气状况。
  
## <a name="weather-bar-overview"></a>天气栏概述
<a name="ol15_weatherbar_overview"> </a>

Outlook 中的天气栏显示某个地理位置的天气状况和预报。用户可以选择一个或多个位置，并在日历模块的天气栏中方便地查看天气数据。图 1 显示了天气栏，其中显示了纽约未来三天的天气预报。 
  
**图 1. Outlook 中的天气栏**

![显示纽约的预报的天气栏。](media/ol15_WeatherBar_fig1.jpg)
  
天气栏的设置与用户的配置文件一起保存。根据 Outlook 帐户的类型，设置可能会随用户在其使用相同配置文件登录的所有计算机上漫游，这与 Exchange 帐户一样。或者，用户也可以像 IMAP/POP 帐户一样，在每台计算机上对设置进行自定义。
  
默认情况下，Outlook 使用 MSN 天气提供的天气数据。天气栏支持遵循指定协议与 Outlook 通信的第三方天气数据 Web 服务。只要第三方天气数据服务支持该协议，用户就可以选择由该天气数据服务在天气栏中提供天气数据。本文介绍了第三方天气服务用于与天气栏中的 Outlook 集成的协议。
  
## <a name="weather-bar-protocol"></a>天气栏协议
<a name="ol15_weatherbar_theprotocol"> </a>

用户可以为天气栏指定不同的天气数据服务，只要该天气数据服务实施的 Web 服务支持以下协议以与 Outlook 通信：
  
1. 天气数据服务支持 Web 服务的基 URL。例如，Contoso 天气 Web 服务的基 URL 可能为 https://service.contoso.com/data.aspx。
    
2. Web 服务允许 Outlook 将以下参数附加到基 URL，以请求位置代码： 
    
   - outputview=search：此参数指示该请求是位置搜索。
    
   - weasearchstr= _city_：此参数指示位置，_城市_（例如，伦敦），用户需要了解该位置的天气预报。
    
   - culture= _LCID_：此参数指示在该计算机上为用户安装的 Office 版本的区域的。 LCID 值是在[用于识别语言的 [RFC4646] 标签](https://www.ietf.org/rfc/rfc4646.txt)中定义的
    
   - src=outlook：此参数指明 Outlook 是请求服务的客户端应用程序。
    
   这些参数允许 Outlook 提取用户感兴趣的位置，并搜索天气数据服务支持的相关位置代码。Web 服务应在 XML 中提供符合 [Outlook Weather Location XML Schema](outlook-weather-location-xml-schema.md)的位置代码，以响应 Outlook。图 2 汇总了位置代码的 Web 服务请求和响应。
    
   **图 2. 位置代码的 Web 服务请求和响应**

   ![天气位置请求和响应](media/ol15_WeatherBar_Fig02.gif)
  
3. Web 服务还允许 Outlook 附加以下参数，以请求某个位置代码的预测信息：
    
   - wealocations= _code_：此参数中的 _code_ 是 Outlook 从步骤 2 中获取的位置代码，该位置代码映射到用户感兴趣的位置。 
    
   - weadegreetype= _degreetype_：此参数指定对温度使用公制还是英制度量单位。 对于 _degreetype_，指定 c 表示公制，f 表示英制。 此参数为可选项，web 服务请求中并不始终会出现此参数。
    
   - culture= _LCID_：此参数指示在该计算机上为用户安装的 Office 版本的区域的。 LCID 值是在[用于识别语言的 [RFC4646] 标签](https://www.ietf.org/rfc/rfc4646.txt)中定义的
    
   - src=outlook：此参数指明 Outlook 是请求服务的客户端应用程序。
    
   这些参数允许 Outlook 使用从步骤 2 返回的位置代码，并请求天气数据服务提供预报。Web 服务应在 XML 中提供符合[Outlook Weather Information XML Schema](outlook-weather-information-xml-schema.md) 的相应天气数据，以响应 Outlook。图 3 汇总了指定位置代码的天气数据 Web 服务请求和响应。
    
   **图 3. 天气信息的 Web 服务请求和响应**

   ![天气信息请求和响应](media/ol15_WeatherBar_Fig03.gif)
  
## <a name="setting-the-weather-bar-to-use-a-weather-service"></a>将天气栏设置为使用天气服务
<a name="ol15_weatherbar_setting"> </a>

管理员或高级用户可以使用 **WeatherServiceUrl** 注册表项对天气栏进行自定义，以使用特定的天气服务。例如，如果 Contoso 天气服务的基 URL 为 https://service.contoso.com/data.aspx，您可以将 **WeatherServiceUrl** 注册表项设置为该 URL。 
  
下表介绍了 **WeatherServiceUrl** 注册表项。 
  
|||
|:-----|:-----|
|**Key** <br/> |HKCU\Software\Microsoft\Office\15.0\Outlook\Options\Calendar  <br/> |
|**值名称** <br/> |**WeatherServiceUrl** <br/> |
|**值类型** <br/> |REG_SZ  <br/> |
|**默认值** <br/> |EMPTY_STRING  <br/> |
|**Description** <br/> |天气数据服务的 URL。  <br/> |
   
## <a name="dependent-conditions"></a>相关条件
<a name="ol15_weatherbar_dependentconditions"> </a>

默认情况下，Outlook 2013 将显示天气栏。本部分介绍了天气栏为何不显示的几个原因。
  
### <a name="weather-bar-is-disabled"></a>天气栏已禁用

首先，确认已在“**Outlook 选项**”对话框的“**日历**”选项卡中选中“**在日历中显示天气**”。 
  
请注意，管理员还可以使用组策略在 Outlook 2013 中完全禁用天气栏，方法是在 Windows 注册表中设置以下项：
  
|||
|:-----|:-----|
|**Key** <br/> |HKCU\Software\Microsoft\Office\15.0\Outlook\Options\Calendar  <br/> |
|**值名称** <br/> |**DisableWeather** <br/> |
|**值类型** <br/> |REG_DWORD  <br/> |
|**默认值** <br/> |0  <br/> |
|**Description** <br/> |值为 0 将启用天气栏，任何其他值将禁用天气栏。  <br/> |
   
If the Weather Bar feature has been disabled by Group Policy, the **Calendar** tab does not include the **Show weather on the calendar** check box. Consult with the administrator to turn the feature back on. 
  
### <a name="office-is-disconnected-from-the-internet"></a>Office 已从 Internet 断开连接

确认 Office 已启用以连接到 Internet—在 Backstage 视图中，转到“信任中心”**** 的“隐私选项”**** 选项卡，确保已选中“允许 Office 连接到 Internet”****。 
  
如果用户已选择不接收 Office 更新，也会禁用天气栏。
  
管理员还可以使用组策略禁用所有联机内容，包括天气栏，方法是在 Windows 注册表中设置以下项：
  
|||
|:-----|:-----|
|**键** <br/> |HKCU\Software\Microsoft\Office\15.0\Common\Internet  <br/> |
|**值名称** <br/> |**UseOnlineContent** <br/> |
|**值类型** <br/> |REG_DWORD  <br/> |
|**默认值** <br/> |双面  <br/> |
|**说明** <br/> |值为 2 将启用天气栏，任何其他值将禁用天气栏。  <br/> |
   
If the Weather Bar feature has been disabled by Group Policy, the **Calendar** tab does not include the **Show weather on the calendar** check box. Consult with the administrator to turn the feature back on. 
  
## <a name="weather-bar-example"></a>天气栏示例
<a name="ol15_weatherbar_example"> </a>

本节显示了 Contoso 天气服务的一个示例，该服务遵循前面的协议与 Outlook 通信。对于用户选择的任何位置，Outlook 首先从 Contoso 天气获取该位置的位置代码，然后使用该位置代码调用 Contoso 天气服务以获取天气数据。
  
### <a name="base-url"></a>基 URL

Contoso 天气为其天气数据服务提供了以下基 URL：
  
https://service.contoso.com/data.aspx
  
### <a name="getting-a-location-code"></a>获取位置代码

Outlook 将步骤 2 中所述的参数附加到基 URL，以获取地理位置  _city_ 的位置代码：
  
https://service.contoso.com/data.aspx?outputview=search&amp;weasearchstr= _city_
  
例如，如果用户在天气栏中选择了 Tokyo，Outlook 将使用以下 URL 从 Contoso 天气获取东京的位置代码： 
  
https://weather.service.contoso.com/data.aspx?outputview=search&amp;weasearchstr=tokyo
  
Contoso 天气使用以下 XML 进行响应，以提供东京的位置代码。XML 符合 Outlook 天气位置 XML 架构。请注意，天气服务通常会返回多个位置的数据（例如，如果所选位置是一个较大的大城市区）。在此示例中，对东京的响应包括两个位置，分别包含在 [weather](weather-element-weatherdata-elementoutlook-weather-location-schema.md) 元素内。相应的位置代码如下所示： 
  
- wc:JAXX0085 表示 **weatherlocationname** 属性为  `Tokyo, JPN`
    
- wc:10038604 表示 **weatherlocationname** 属性为  `Shinjuku-ku, Tokyo, Japan`
    
```XML
<?xml version="1.0" ?>
<weatherdata>
  <weather weatherlocationcode="wc:JAXX0085" 
    weatherlocationname="Tokyo, JPN">
  </weather>
  <weather weatherlocationcode="wc:10038604" 
    weatherlocationname="Shinjuku-ku, JPN">
  </weather>
</weatherdata>

```

### <a name="getting-weather-information-for-a-location-code"></a>获取位置代码的天气信息

获取位置的位置代码后，Outlook 会将步骤 3 中的参数附加到基 URL，以获取该位置代码的天气信息。
  
https://service.contoso.com/data.aspx?wealocations= _code_
  
例如，如果 Outlook 已从 Contoso 天气为 Tokyo 获取位置代码 wc:JAXX0085，Outlook 将在以下 URL 中使用此位置代码获取天气信息。
  
https://service.contoso.com/data.aspx?wealocations=wc:JAXX0085
  
Contoso 天气使用以下 XML 进行响应，以提供东京的位置代码的天气信息。 XML 符合 Outlook 天气信息 XML 架构。
  
```XML
<?xml version="1.0"?>
<weatherdata>
  <weather timezone="9" attribution="Data provided by Trey Research" 
    degreetype="F" imagerelativeurl="https://contoso.com/images/en-us/" 
    url="https://contoso.com/weather.aspx?eid=33568&amp;q=Tokyo-JPN" 
    weatherlocationname="Tokyo, JPN" 
    weatherlocationcode="wc:JAXX0085">
      <current winddisplay="9 mph NNW" windspeed="9" humidity="90" feelslike="44" 
        observationpoint="Tokyo" observationtime="06:00:00" 
        shortday="Sat" day="Saturday" date="2012-04-14" skytext="Rain" skycode="11" 
        temperature="48"/>
      <forecast shortday="Sat" day="Saturday" date="2012-04-14" precip="95" skytextday="Rain"
        skycodeday="11" high="55" low="47"/>
      <forecast shortday="Sun" day="Sunday" date="2012-04-15" precip="5" skytextday="Partly Cloudy" 
        skycodeday="30" high="65" low="43"/>
      <forecast shortday="Mon" day="Monday" date="2012-04-16" precip="5" skytextday="Partly Cloudy" 
        skycodeday="30" high="64" low="52"/>
      <forecast shortday="Tue" day="Tuesday" date="2012-04-17" precip="70" skytextday="Showers / Clear" 
        skycodeday="39" high="66" low="53"/>
      <forecast shortday="Wed" day="Wednesday" date="2012-04-18" precip="55" skytextday="Showers / Clear" 
        skycodeday="39" high="68" low="51"/>
  </weather>
</weatherdata>

```

### <a name="resetting-outlook-to-use-msn-weather"></a>将 Outlook 重置为使用 MSN 天气

尽管 Outlook 默认使用 MSN 天气，但是如果用户对天气栏进行自定义以使用其他天气服务，随后又想使用 MSN 天气，用户只需在 Windows 注册表中删除 **WeatherServiceUrl** 项即可。删除此注册表项即可将 Outlook 重置为使用 MSN 天气。 
  
## <a name="conclusion"></a>结束语
<a name="ol15_weatherbar_conclusion"> </a>

Outlook 日历中的天气栏默认使用 MSN 天气来提供指定位置的天气预报。用户可以方便地查看所关注位置的天气信息。如果第三方天气数据服务支持 Outlook 天气位置 XML 架构和 Outlook 天气信息 XML 架构，并遵循与 Outlook 的简单 Web 服务协议，则也可与天气栏集成。
  
## <a name="see-also"></a>另请参阅

- [Outlook 天气位置 XML 架构](outlook-weather-location-xml-schema.md)   
- [Outlook Weather Information XML Schema](outlook-weather-information-xml-schema.md)
    

