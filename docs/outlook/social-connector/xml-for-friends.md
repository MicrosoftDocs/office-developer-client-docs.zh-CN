---
title: 好友的 XML
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3362639a-8098-47ab-ba94-ee89e4920032
description: Microsoft Outlook Social Connector (.osc) 提供程序 XML 架构中的 "好友" 元素允许 .osc 提供程序指定与社交网络中的 Outlook 用户相关联的人员列表的相关信息。
ms.openlocfilehash: df3bf03c5fd1dcdac3096411bc60bcb1eeec661e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361157"
---
# <a name="xml-for-friends"></a>好友的 XML

Microsoft Outlook Social Connector (.osc) 提供程序 XML 架构中的 "**好友**" 元素允许 .osc 提供程序指定与社交网络中的 Outlook 用户相关联的人员列表的相关信息。 如果 .osc 提供程序支持缓存同步, 则此人列表将仅包含社交网络上的 Outlook 用户的好友。 如果 .osc 支持按需同步或混合同步, 则此列表可能包含 Outlook 用户的好友和非好友。 

列表中的每个人都表示为 XML 架构中的**person**元素, 该元素支持诸如名字、姓氏和电子邮件地址等详细信息。 .osc 提供商使用**好友**和**person**元素, 而不考虑他们希望 .osc 从社交网络同步好友信息的方式。 请注意, **person**的子元素类似于 outlook 联系人的一些属性, 这有助于在社交网络支持缓存或混合的情况下将好友存储在特定于社交网络的 outlook 联系人文件夹中。将朋友同步到 Outlook 联系人文件夹。 

## <a name="example-scenarios"></a>示例场景

以下示例方案显示了 .osc 提供程序实现的 .osc 提供程序可扩展性 API 调用和 .osc 获取了友元信息。 信息以符合 .osc 提供程序 XML 架构的 XML 字符串表示。
  
有关友元 xml 的示例, 请参阅[好友 xml 示例](friends-xml-example.md)。 有关同步好友信息的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。

### <a name="scenario-1-get-a-list-of-friends"></a>方案 1: 获取好友列表

方案 1-.osc 获取好友列表、 [ISocialPerson](isocialpersoniunknown.md)对象和每个朋友的图片: 
    
1. 支持通过社交网络网站显示好友并允许 .osc 缓存友元信息的 .osc 提供程序指示通过使用**getFriends**和 cacheFriends 元素 (这些子元素是**** **功能**元素。 
    
2. .osc 提供程序还实现了[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)、 [ISocialSession:: GetPerson](isocialsession-getperson.md)、 [ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)和[ISocialPerson:: GetPicture](isocialperson-getpicture.md)方法。 
    
3. .osc 调用**ISocialProvider:: GetCapabilities**检查以下元素的值: **getFriends**验证 .osc 提供程序是否支持显示社交网络中的好友, 以及**cacheFriends**验证提供程序支持缓存好友。 
    
4. .osc 调用**ISocialSession:: GetPerson**获取 Outlook 用户的**ISocialPerson**对象。 
    
5. .osc 调用**ISocialPerson:: GetFriendsAndColleagues**获取在_personCollection_参数字符串中返回的 Outlook 用户的好友列表。 _personCollection_字符串符合 xml 架构中的**好友**元素的 XML 架构定义。 
    
6. 对于_personCollection_ XML 字符串中的每个朋友, .osc 获取**userID**元素的值, 以调用**ISocialSession:: GetPerson**获取该好友的**ISocialPerson**对象。 
    
7. 对于**personCollection** XML 字符串中的每个朋友, .osc 调用[ISocialPerson:: GetPicture](isocialperson-getpicture.md)获取该好友的图片资源。 
    
   .osc 可以对**ISocialPerson**对象进行进一步的调用, 以获取该朋友的活动和详细信息 (例如, 电子邮件地址)。 
    
### <a name="scenario-2-synchronize-friends"></a>方案 2: 同步好友 

方案 2-.osc 动态同步朋友:
    
1. 支持对友元和非好友同步的 .osc 提供程序使用**getFriends**和**dynamicContactsLookup**元素指示对 .osc 的请求。 .osc 提供程序还设置了**hashFunction**元素。 所有三个元素都是**功能**的子元素。 
    
2. .osc 提供程序还实现了[ISocialSession2:: GetPeopleDetails](isocialsession2-getpeopledetails.md)方法。 
    
3. .osc 调用**ISocialProvider:: GetCapabilities**检查**getFriends**和**dynamicContactsLookup**的值, 以验证该 .osc 提供商是否支持朋友和非好友的按需同步。 .osc 还记录了 .osc 提供商支持的**hashFunction**的值。 
    
4. 对于 "人员" 窗格中显示的每个用户, .osc 都会收集用户的电子邮件地址, 并使用**hashFunction**中指定的哈希函数对其进行加密。 这构成了符合**hashedAddresses**元素的 xml 架构定义的 xml 字符串。 
    
5. .osc 调用**ISocialSession2:: GetPeopleDetails**, 将哈希地址的 XML 字符串提供为_personAddresses_参数, 以在_personsCollection_参数中动态获取人员的更新详细信息。 _personsCollection_参数字符串符合 xml 架构中的**好友**元素的 XML 架构定义。 

## <a name="parent-and-child-elements"></a>父元素和子元素

以下是**友元**架构中的两个顶级元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**老朋友** <br/> |表示**person**元素列表的根元素。 **ISocialPerson:: GetFriendsAndColleagues**、 [ISocialSession:: FindPerson](isocialsession-findperson.md)和**ISocialSession2:: GetPeopleDetails**返回符合**好友**元素的架构定义的 XML 字符串。  <br/> |
|**person** <br/> |代表**person**元素列表中的一个人员。 [ISocialPerson:: GetDetails](isocialperson-getdetails.md)方法返回符合**person**元素的架构定义的 XML 字符串。  <br/> |
   
下表介绍了 .osc 提供程序 XML 架构中**person**元素的每个子元素。 
  
有关 .osc 提供程序 XML 架构的完整定义 (包括哪些元素是必需元素或可选的元素), 请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。
  
|**元素**|**说明**|
|:-----|:-----|
|**address** <br/> |人员的实际街道地址。  <br/> |
|**日** <br/> |人员事件的周年纪念日期。  <br/> |
|**askmeabout** <br/> |人员感兴趣或专业知识的主题。  <br/> |
|**一定** <br/> |人员的出生日期。  <br/> |
|**businessAddress** <br/> |人员工作场所的物理街道地址。  <br/> |
|**businessCity** <br/> |人员的工作场所所在的城市。  <br/> |
|**businessCountryOrRegion** <br/> |人员的工作场所所在的国家或地区。  <br/> |
|**businessState** <br/> |人员的工作场所的省/市/自治区。  <br/> |
|**businessZip** <br/> |人员的工作场所的邮政编码。  <br/> |
|**单元** <br/> |人员的移动电话号码。  <br/> |
|**城市** <br/> |人员的实际地址所在的城市。  <br/> |
|**company** <br/> |与人员关联的公司的名称。  <br/> |
|**countryOrRegion** <br/> |人员的实际地址所在的国家或地区。  <br/> |
|**creationTime** <br/> |社交网络中个人个人资料的创建时间。  <br/> |
|**emailAddress** <br/> |人员的主电子邮件地址。  <br/> |
|**emailAddress2** <br/> |人员的辅助电子邮件地址。  <br/> |
|**emailAddress3** <br/> |人员的第三个电子邮件地址。  <br/> |
|**expirationTime** <br/> |社交网络上个人的配置文件数据到期的时间。  <br/> |
|**fileAs** <br/> |在 Outlook 联系人文件中将此人作为联系人进行存档的字符串。  <br/> |
|**firstName** <br/> |名字或人员的名字。  <br/> |
|**friendStatus** <br/> |此人与社交网络上登录用户的好友状态。 必须为以下值之一: **friend**、 **nonfriend**、 **pending**、 **pendingin**、 **pendingout**。  <br/> |
|**fullName** <br/> |人员的全名。  <br/> |
|**之类** <br/> |个人的性别。 必须为下列值之一: "**男**"、"**女**"、"**未指定**"。  <br/> |
|**homePhone** <br/> |人员的家庭电话号码。  <br/> |
|**index** <br/> |在传递给**ISocialSession2:: GetPeopleDetails**方法的调用的_personsAddresses_字符串参数中个人的哈希地址的位置。 它还指示**GetPeopleDetails**返回的**** _personsCollection_字符串中的人员的 XML。  <br/> |
|**型** <br/> |人员参与的行业。  <br/> |
|**interests** <br/> |此人的兴趣或业余爱好。  <br/> |
|**lastModificationTime** <br/> |用户的个人资料上次在社交网络上进行修改的时间。  <br/> |
|**lastName** <br/> |用户的姓或名。  <br/> |
|**location** <br/> |人员的位置。  <br/> |
|**昵称** <br/> |人员的名称较短或名称。  <br/> |
|**otherAddress** <br/> |人员的备选街道地址。  <br/> |
|**otherCity** <br/> |人员的备选地址所在的城市。  <br/> |
|**otherCountryOrRegion** <br/> |个人备选地址所在的国家或地区。  <br/> |
|**otherState** <br/> |某人的备选地址的省/市/自治区。  <br/> |
|**otherZip** <br/> |某人的备选地址的邮政编码。  <br/> |
|**电话** <br/> |人员的主要联系人电话号码。  <br/> |
|**pictureUrl** <br/> |个人的个人资料图片的 URL。  <br/> |
|**相互** <br/> |此人与已登录用户的关系。  <br/> |
|**schools** <br/> |人员要转到或转到的学校。  <br/> |
|**skills** <br/> |人员的个人技能。  <br/> |
|**state** <br/> |人员的实际地址的省/市/自治区。  <br/> |
|**title** <br/> |添加到人员姓名中的标志。  <br/> |
|**userID** <br/> |标识社交网络上的人员的 ID。  <br/> |
|**webProfilePage** <br/> |包含人员个人资料的网页地址。  <br/> |
|**下载** <br/> |人员网站。  <br/> |
|**workPhone** <br/> |人员的商务电话号码。  <br/> |
|**邮政编码** <br/> |人员的实际地址的邮政编码。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [友元 XML 示例](friends-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [XML 的功能](xml-for-capabilities.md) 
- [适用于活动的 XML](xml-for-activities.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

