---
title: 好友的 XML
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3362639a-8098-47ab-ba94-ee89e4920032
description: Microsoft Outlook Social Connector (OSC) 提供程序 XML 架构中的 friends 元素允许 OSC 提供程序指定与社交网络中的 Outlook 用户关联的人员列表的信息。
ms.openlocfilehash: df3bf03c5fd1dcdac3096411bc60bcb1eeec661e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361157"
---
# <a name="xml-for-friends"></a>好友的 XML

Microsoft Outlook Social Connector (OSC) 提供程序 XML 架构中的 **friends** 元素允许 OSC 提供程序指定与社交网络中的 Outlook 用户关联的人员列表的信息。 如果 OSC 提供程序支持缓存同步，则此人员列表将仅包含社交网络Outlook用户的好友。 如果 OSC 支持按需同步或混合同步，则此列表可能包含用户好友Outlook好友。 

列表中的每个人都表示为 XML 架构中的 **person** 元素，该元素支持诸如名字、姓氏和电子邮件地址等详细信息。 OSC 提供程序使用 **好友和****人员** 元素，而不管他们希望 OSC 如何从社交网络同步好友信息。 请注意，人的子元素类似于Outlook 联系人的一些属性，如果社交网络支持好友到 Outlook 联系人文件夹的缓存或混合同步，则便于将好友存储在特定于社交网络的 Outlook 联系人文件夹中。 

## <a name="example-scenarios"></a>示例场景

以下示例方案显示 OSC 提供程序实现和 OSC 为获取好友信息而进行的操作系统C 提供程序扩展性 API 调用。 信息以符合 OSC 提供程序 XML 架构的 XML 字符串表示。
  
有关好友 XML 的示例，请参阅 [好友 XML 示例](friends-xml-example.md)。 有关同步好友信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。

### <a name="scenario-1-get-a-list-of-friends"></a>方案 1：获取好友列表

方案 1 — OSC 获取好友列表 [、ISocialPerson](isocialpersoniunknown.md) 对象以及每个好友的图片： 
    
1. 支持显示社交网络网站中的好友并允许 OSC 缓存好友信息的 OSC 提供程序使用 **getFriends** 和 **cacheFriends** 元素向 OSC 指明这一点，这两个元素是 **capabilities** 元素的子元素。 
    
2. OSC 提供程序还实现 ISocialProvider：：GetCapabilities、ISocialSession：：GetPerson、ISocialPerson：：GetFriendsAndColleagues 和[ISocialPerson：：GetPicture](isocialperson-getpicture.md)方法。 [](isocialprovider-getcapabilities.md) [](isocialsession-getperson.md) [](isocialperson-getfriendsandcolleagues.md) 
    
3. OSC 调用 **ISocialProvider：：GetCapabilities** 来检查以下元素的值 **：getFriends** 验证 OSC 提供程序是否支持显示社交网络中的好友 **，cacheFriends** 验证提供程序是否支持缓存好友。 
    
4. OSC 调用 **ISocialSession：：GetPerson** 为用户获取 **ISocialPerson** Outlook对象。 
    
5. OSC 调用 **ISocialPerson：：GetFriendsAndColleagues，** 获取在 _personCollection_ 参数字符串中返回的 Outlook 用户的好友列表。 _personCollection_ 字符串符合 XML 架构中 **friends** 元素的 XML 架构定义。 
    
6. 对于  _personCollection_ XML 字符串中的每个好友，OSC 获取 **userID** 元素的值以调用 **ISocialSession：：GetPerson** 以获取该好友的 **ISocialPerson** 对象。 
    
7. 对于 **personCollection** XML 字符串中的每个好友，OSC 调用 [ISocialPerson：：GetPicture](isocialperson-getpicture.md) 获取该好友的图片资源。 
    
   OSC 可以进一步调用 **ISocialPerson** 对象，以获取活动和详细信息 (例如，该好友) 的电子邮件地址。 
    
### <a name="scenario-2-synchronize-friends"></a>方案 2：同步好友 

方案 2 - OSC 动态同步好友：
    
1. 支持好友和非好友的按需同步的 OSC 提供程序使用 **getFriends** 和 **dynamicContactsLookup** 元素将指示到 OSC。 OSC 提供程序还会设置 **hashFunction** 元素。 所有三个元素都是功能的 **子元素**。 
    
2. OSC 提供程序还实现 [ISocialSession2：：GetPeopleDetails](isocialsession2-getpeopledetails.md) 方法。 
    
3. OSC 调用 **ISocialProvider：：GetCapabilities** 来检查 **getFriends** 和 **dynamicContactsLookup** 的值，以验证 OSC 提供程序是否支持好友和非好友的按需同步。 OSC 还记下 OSC 提供程序支持的 **hashFunction** 的值。 
    
4. 对于显示在人员窗格中的每个用户，OSC 会收集用户的电子邮件地址，然后使用 **hashFunction** 中指定的哈希函数对其进行加密。 这将形成一个 XML 字符串，该字符串符合 **hashedAddresses** 元素的 XML 架构定义。 
    
5. OSC 调用 **ISocialSession2：：GetPeopleDetails，** 以  _personAddresses_ 参数形式提供此哈希地址的 XML 字符串，以动态获取  _personCollection_ 参数中人员的更新详细信息。 _personsCollection_ 参数字符串符合 XML 架构中 **friends** 元素的 XML 架构定义。 

## <a name="parent-and-child-elements"></a>父元素和子元素

以下是好友架构中的两个 **顶级** 元素。 
  
|**元素**|**说明**|
|:-----|:-----|
|**好友** <br/> |表示人员元素列表的 **根** 元素。 **ISocialPerson：：GetFriendsAndColleagues、ISocialSession：：FindPerson** 和 **ISocialSession2：：GetPeopleDetails** 返回符合 **好友** 元素的架构定义的 XML 字符串。 [](isocialsession-findperson.md)  <br/> |
|**person** <br/> |表示人员元素列表中的 **一** 个人。 [ISocialPerson：：GetDetails](isocialperson-getdetails.md)方法返回一个 XML 字符串，该字符串符合 **person** 元素的架构定义。  <br/> |
   
下表介绍了 OSC 提供程序 XML 架构 **中 person** 元素的每个子元素。 
  
有关 OSC 提供程序 XML 架构的完整定义，包括哪些元素是必需的或可选的，请参阅Outlook[连接器提供程序 XML 架构。](outlook-social-connector-provider-xml-schema.md)
  
|**元素**|**说明**|
|:-----|:-----|
|**address** <br/> |人员的物理街道地址。  <br/> |
|**周年** <br/> |人员事件的周年日期。  <br/> |
|**askmeabout** <br/> |人员感兴趣的主题或专长。  <br/> |
|**birthday** <br/> |人员出生日期。  <br/> |
|**businessAddress** <br/> |人员工作区的物理街道地址。  <br/> |
|**businessCity** <br/> |用于个人工作场所的城市。  <br/> |
|**businessCountryOrRegion** <br/> |人员工作场所的一个或多个国家/地区。  <br/> |
|**businessState** <br/> |人员工作场所的省/市/县。  <br/> |
|**businessZip** <br/> |人员工作区的邮政编码。  <br/> |
|**cell** <br/> |人员的移动电话号码。  <br/> |
|**城市** <br/> |人员物理地址的城市。  <br/> |
|**company** <br/> |与此人关联的公司的名称。  <br/> |
|**countryOrRegion** <br/> |人员物理地址的"国家/地区"或"地区"。  <br/> |
|**creationTime** <br/> |社交网络上人员个人资料的创建时间。  <br/> |
|**emailAddress** <br/> |人员的主电子邮件地址。  <br/> |
|**emailAddress2** <br/> |人员辅助电子邮件地址。  <br/> |
|**emailAddress3** <br/> |人员的第三个电子邮件地址。  <br/> |
|**expirationTime** <br/> |用户的个人资料数据在社交网络上的过期时间。  <br/> |
|**fileAs** <br/> |要作为联系人存档在联系人文件中Outlook字符串。  <br/> |
|**firstName** <br/> |人员的名字或名字。  <br/> |
|**friendStatus** <br/> |此用户在社交网络上具有已登录用户的好友状态。 必须为以下值之一：friend、nonfriend、pending、pendingin、pendingout 。      <br/> |
|**fullName** <br/> |人员的完整姓名。  <br/> |
|**gender** <br/> |人员性别。 必须是以下值之一：**男性、****男性****、未指定**。  <br/> |
|**homePhone** <br/> |人员住宅电话号码。  <br/> |
|**index** <br/> |人员哈希地址在  _personAddresses_ 字符串参数中的位置，该参数传递给 **对 ISocialSession2：：GetPeopleDetails** 方法的调用。 它还指示人员在 **GetPeopleDetails** 返回的 _personCollection_ 字符串中的人员 XML。   <br/> |
|**industries** <br/> |人员参与的行业。  <br/> |
|**interests** <br/> |人员的兴趣或爱好。  <br/> |
|**lastModificationTime** <br/> |上次在社交网络上修改用户个人资料的时间。  <br/> |
|**lastName** <br/> |人员姓氏或姓氏。  <br/> |
|**location** <br/> |人员的位置。  <br/> |
|**nickname** <br/> |人员的姓名或姓名越短。  <br/> |
|**otherAddress** <br/> |该人员的替代街道地址。  <br/> |
|**otherCity** <br/> |人员备用地址的城市。  <br/> |
|**otherCountryOrRegion** <br/> |用户备用地址的"国家/地区"。  <br/> |
|**otherState** <br/> |人员备用地址的省/市/县。  <br/> |
|**otherZip** <br/> |人员备用地址的邮政编码。  <br/> |
|**phone** <br/> |人员的主要联系人电话号码。  <br/> |
|**pictureUrl** <br/> |人员的个人资料图片的 URL。  <br/> |
|**关系** <br/> |此人与登录用户的关系。  <br/> |
|**schools** <br/> |人员前往或转到的学校。  <br/> |
|**skills** <br/> |人员的个人技能。  <br/> |
|**state** <br/> |人员物理地址的省/市/县。  <br/> |
|**title** <br/> |添加到人员姓名的指定。  <br/> |
|**userID** <br/> |用于标识社交网络上人员的 ID。  <br/> |
|**webProfilePage** <br/> |包含人员个人资料的网页地址。  <br/> |
|**website** <br/> |人员的网站。  <br/> |
|**workPhone** <br/> |人员商务电话号码。  <br/> |
|**zip** <br/> |人员物理地址的邮政编码。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [好友 XML 示例](friends-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [功能的 XML](xml-for-capabilities.md) 
- [活动的 XML](xml-for-activities.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

