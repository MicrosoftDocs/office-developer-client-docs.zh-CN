---
title: 朋友 XML
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3362639a-8098-47ab-ba94-ee89e4920032
description: Microsoft Outlook Social Connector (OSC) 提供程序的 XML 架构中的朋友元素允许 OSC 提供程序指定的列表与社交网络中的 Outlook 用户关联的人员的信息。
ms.openlocfilehash: 07f1bb77e7912e3973fd2af8a70275642b72039c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779354"
---
# <a name="xml-for-friends"></a>朋友 XML

Microsoft Outlook Social Connector (OSC) 提供程序的 XML 架构中的**朋友**元素允许 OSC 提供程序指定的列表与社交网络中的 Outlook 用户关联的人员的信息。 如果 OSC 提供程序支持缓存的同步，此列表的人员将包含仅朋友社交网络上的 Outlook 用户。 如果 OSC 支持点播或混合同步，此列表可能包含朋友和非朋友 Outlook 用户。 

列表中的每个人都表示为 XML 架构，支持如名字、 姓氏和电子邮件地址的详细信息中的**人员**元素。 OSC 提供程序使用**朋友**和**人员**元素而不考虑希望 OSC 同步朋友信息，请从社交网络的方式。 请注意，类似于某些 Outlook 联系人，从而便于将朋友特定的 Outlook 联系人文件夹中存储到社交网络中，如果社交网络支持缓存的属性或混合**人**的子元素朋友的 Outlook 联系人文件夹的同步。 

## <a name="example-scenarios"></a>示例方案

下面的示例方案显示 OSC 提供程序扩展性 API 调用 OSC 提供程序实现并 OSC 使获取朋友信息。 符合 OSC 提供程序的 XML 架构的 XML 字符串中表示的信息。
  
朋友 XML 的示例，请参阅[朋友 XML 示例](friends-xml-example.md)。 有关同步朋友的信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。

### <a name="scenario-1-get-a-list-of-friends"></a>方案 1： 获取朋友的列表

方案 1 — OSC 获取每个朋友朋友和[ISocialPerson](isocialpersoniunknown.md)对象和图片的列表： 
    
1. OSC 提供程序的支持显示从社交网络站点的朋友和允许缓存朋友信息 OSC 指示到 OSC 使用**getFriends**和**cacheFriends**元素，它们是**的子元素功能**元素。 
    
2. OSC 提供程序还实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)、 [ISocialSession::GetPerson](isocialsession-getperson.md)、 [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)和[ISocialPerson::GetPicture](isocialperson-getpicture.md)方法。 
    
3. OSC 调用**ISocialProvider::GetCapabilities**检查以下元素的值： **getFriends**以验证 OSC 提供程序支持显示从社交网络和**cacheFriends**朋友以验证提供程序缓存朋友的支持。 
    
4. OSC 调用**ISocialSession::GetPerson** Outlook 用户获取**ISocialPerson**对象。 
    
5. OSC 调用**ISocialPerson::GetFriendsAndColleagues**来获取 Outlook 用户_personCollection_参数字符串中返回的朋友列表。 _PersonCollection_字符串符合 XML 架构定义中的 XML 架构的**朋友**元素。 
    
6. 为_personCollection_ XML 字符串中每个朋友，OSC 获取呼叫**ISocialSession::GetPerson**获取该朋友**ISocialPerson**对象的**userID**元素的值。 
    
7. 对于**personCollection** XML 字符串中每个朋友，OSC 调用[ISocialPerson::GetPicture](isocialperson-getpicture.md)获取该朋友图片资源。 
    
   OSC 可以进行进一步的**ISocialPerson**对象上的呼叫以获取活动和详细信息 （例如，电子邮件地址） 的好友。 
    
### <a name="scenario-2-synchronize-friends"></a>方案 2： 同步朋友 

方案 2-OSC 同步朋友动态：
    
1. OSC 提供程序支持的朋友和非朋友组成的按需同步指示的可以 OSC，通过使用**getFriends**和**dynamicContactsLookup**元素。 OSC 提供程序还设置**hashFunction**元素。 所有三个元素均**功能**的子元素。 
    
2. OSC 提供程序还实现[ISocialSession2::GetPeopleDetails](isocialsession2-getpeopledetails.md)方法。 
    
3. OSC 调用**ISocialProvider::GetCapabilities**检查**getFriends**和**dynamicContactsLookup**验证 OSC 提供程序支持朋友和朋友和非朋友的按需同步的值。 OSC 还使**hashFunction** OSC 提供程序支持的值的注释。 
    
4. 为人员窗格中显示每个用户，OSC 收集用户的电子邮件地址，并使用**hashFunction**中指定的哈希函数对它进行加密。 此表单符合**hashedAddresses**元素的 XML 架构定义一个 XML 字符串。 
    
5. OSC 调用**ISocialSession2::GetPeopleDetails**，提供该 XML 字符串的哈希地址作为_personAddresses_参数，以便对_personsCollection_参数中的动态获得更新的详细信息。 _PersonsCollection_参数字符串符合 XML 架构定义中的 XML 架构的**朋友**元素。 

## <a name="parent-and-child-elements"></a>父和子元素

以下是**朋友**架构中的两个顶级元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**朋友** <br/> |代表一个**人**元素的列表的根元素。 **ISocialPerson::GetFriendsAndColleagues**、 [ISocialSession::FindPerson](isocialsession-findperson.md)和**ISocialSession2::GetPeopleDetails**返回到**朋友**元素的架构定义符合的 XML 字符串。  <br/> |
|**person** <br/> |代表一个**人**元素的列表中的某个人。 [ISocialPerson::GetDetails](isocialperson-getdetails.md)方法返回与**人**元素的架构定义的 XML 字符串，符合。  <br/> |
   
下表介绍**人员**元素 OSC 提供程序的 XML 架构中的每个子元素。 
  
有关完整定义 OSC 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。
  
|**元素**|**说明**|
|:-----|:-----|
|**地址** <br/> |人员的物理街道地址。  <br/> |
|**周年日** <br/> |周年日的人事件的日期。  <br/> |
|**askmeabout** <br/> |利息或的人员的专业知识的主题。  <br/> |
|**生日** <br/> |人员出生日期。  <br/> |
|**businessAddress** <br/> |此人的工作区的物理街道地址。  <br/> |
|**businessCity** <br/> |此人的工作区的城市。  <br/> |
|**businessCountryOrRegion** <br/> |国家或地区的人员的工作区。  <br/> |
|**businessState** <br/> |省或自治区的人的工作区。  <br/> |
|**businessZip** <br/> |邮政编码的人的工作区。  <br/> |
|**单元格** <br/> |此人的移动电话号码。  <br/> |
|**市/县** <br/> |此人的物理地址的城市。  <br/> |
|**公司** <br/> |与联系人关联的公司名称。  <br/> |
|**countryOrRegion** <br/> |国家或地区的物理地址的联系人。  <br/> |
|**creationTime** <br/> |社交网络上的人员配置文件的创建时间。  <br/> |
|**emailAddress** <br/> |人员的主电子邮件地址。  <br/> |
|**emailAddress2** <br/> |此人辅助电子邮件地址。  <br/> |
|**emailAddress3** <br/> |此人三级的电子邮件地址。  <br/> |
|**expirationTime** <br/> |此人的配置文件数据过期社交网络的时间。  <br/> |
|**fileAs** <br/> |此人的如 Outlook 中的某个联系人联系人文件存档的字符串。  <br/> |
|**firstName** <br/> |名字或给定的人员的姓名。  <br/> |
|**friendStatus** <br/> |朋友的社交网络上登录用户与此人的状态。 必须为下列值之一：**朋友**、 **nonfriend**、**挂起**、 **pendingin**、 **pendingout**。  <br/> |
|**fullName** <br/> |此人的完整名称。  <br/> |
|**性别** <br/> |人员的性别。 必须为下列值之一：**男**、**女**、**未指定**。  <br/> |
|**住宅电话** <br/> |该联系人的住宅电话号码。  <br/> |
|**index** <br/> |此人的哈希地址_personsAddresses_字符串参数中的位置传递到调用**ISocialSession2::GetPeopleDetails**方法。 它还指示此人的**人员**XML 中返回**GetPeopleDetails** _personsCollection_字符串。  <br/> |
|**行业** <br/> |此人正在从事的行业。  <br/> |
|**兴趣** <br/> |兴趣或爱好的人员。  <br/> |
|**lastModificationTime** <br/> |社交网络上次修改此人的配置文件的时间。  <br/> |
|**lastName** <br/> |姓氏或联系人的姓。  <br/> |
|**位置** <br/> |人员的位置。  <br/> |
|**昵称** <br/> |较短的名称或虚构的人员的姓名。  <br/> |
|**otherAddress** <br/> |替代的人员的街道地址。  <br/> |
|**otherCity** <br/> |此人的替代地址的城市。  <br/> |
|**otherCountryOrRegion** <br/> |国家或地区的替代此人的地址。  <br/> |
|**otherState** <br/> |省或自治区的替代此人的地址。  <br/> |
|**otherZip** <br/> |邮政编码的替代此人的地址。  <br/> |
|**电话** <br/> |此人的主要联系人的电话号码。  <br/> |
|**pictureUrl** <br/> |URL 的人员配置文件图片。  <br/> |
|**关系** <br/> |在用户登录与此人的关系。  <br/> |
|**学校** <br/> |学校的联系人转或拿起。  <br/> |
|**技能** <br/> |个人的人员的技能。  <br/> |
|**state** <br/> |省或自治区的物理地址的联系人。  <br/> |
|**title** <br/> |指定添加到此人的姓名。  <br/> |
|**用户 Id** <br/> |若要确定社交网络中的人的 ID。  <br/> |
|**webProfilePage** <br/> |包含的人员配置文件的网页地址。  <br/> |
|**网站** <br/> |此人的网站。  <br/> |
|**workPhone** <br/> |商务电话号码的人员。  <br/> |
|**zip** <br/> |邮政编码或邮政编码的物理地址的联系人。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [朋友 XML 示例](friends-xml-example.md)  
- [同步朋友和活动](synchronizing-friends-and-activities.md)  
- [功能 XML](xml-for-capabilities.md) 
- [活动的 XML](xml-for-activities.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

