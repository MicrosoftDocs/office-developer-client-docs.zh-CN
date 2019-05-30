---
title: 好友 XML 示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 83afbdef-4f12-4673-a0c1-bbf86274558f
description: '本主题中的 XML 示例是在调用 ISocialPerson:: GetFriendsAndColleagues 方法后返回到 Outlook Social Connector (.OSC) 的友元 XML 字符串。 该示例显示了两个好友的好友 XML, 每个好友由 person 元素分隔。 每个友元指定社交网络上 userID 元素的唯一值。'
ms.openlocfilehash: 593019ec4dcd1b9b578bfe275fb8e6664bbd11a9
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542224"
---
# <a name="friends-xml-example"></a>好友 XML 示例

本主题中的 XML 示例是在调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法后返回到 Outlook Social CONNECTOR (.osc) 的友元 xml 字符串。 该示例显示了两个好友的**好友**XML, 每个好友由**person**元素分隔。 每个友元指定社交网络上**userID**元素的唯一值。 
  
**友元**XML 的其余元素具有自解释的名称。 有关这些元素的详细说明, 请参阅[适用于好友的 XML](xml-for-friends.md)。 
  
## <a name="xml-example"></a>XML 示例

下面的示例展示了社交网络中两个人的**好友**XML。 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<friends xmlns="http://schemas.microsoft.com/office/outlook/2010/06/socialprovider.xsd">
  <person>
    <userID>4667647</userID>
    <firstName>Melissa</firstName>
    <lastName>MacBeth</lastName>
    <nickname></nickname>
    <fileAs>MacBeth, Melissa (Contoso Ltd.)</fileAs>
    <company>Contoso Ltd.</company>
    <title>Product Manager</title>
    <anniversary>2005-05-17</anniversary>
    <birthday>1979-08-09</birthday>
    <emailAddress>melissa@contoso.com</emailAddress>
    <emailAddress2>melissa@fabrikam.com</emailAddress2>
    <emailAddress3>melissa@adventureworks.com</emailAddress3>
    <webProfilePage>https://contoso.com/melissa</webProfilePage>
    <phone>800-555-1212</phone>
    <cell>888-555-1212</cell>
    <workPhone>425-555-1212</workPhone>
    <creationTime>2010-01-08T08:30:20-08:00</creationTime>
    <lastModificationTime>2010-01-08T11:40:14-08:00</lastModificationTime>
    <expirationTime>2010-01-09T11:40:14-08:00</expirationTime>
    <gender>female</gender>
    <index>0</index>
  </person>
  <person>
    <userID>5015012</userID>
    <firstName>Michael</firstName>
    <lastName>Affronti</lastName>
    <nickname>Mr. Social</nickname>
    <fileAs>Affronti, Michael (Contoso Ltd.)</fileAs>
    <company>Contoso Ltd.</company>
    <title>Sales Director</title>
    <anniversary>2009-06-21</anniversary>
    <birthday>1980-09-10</birthday>
    <emailAddress>michael@contoso.com</emailAddress>
    <emailAddress2>michael@fabrikam.com</emailAddress2>
    <emailAddress3>michael@adventureworks.com</emailAddress3>
    <webProfilePage>https://contoso.com/michael</webProfilePage>
    <phone>800-555-1212</phone>
    <cell>888-555-1212</cell>
    <workPhone>425-555-1212</workPhone>
    <creationTime>2010-01-08T08:30:20-08:00</creationTime>
    <lastModificationTime>2010-01-08T11:40:14-08:00</lastModificationTime>
    <expirationTime>2010-01-09T11:40:14-08:00</expirationTime>
    <gender>male</gender>
    <index>1</index>
  </person>
</friends>

```

## <a name="see-also"></a>另请参阅

- [.OSC 提供程序 XML 示例](osc-provider-xml-examples.md)  
- [功能 XML 示例](capabilities-xml-example.md) 
- [活动源 XML 示例](activity-feed-xml-example.md) 
- [Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)

