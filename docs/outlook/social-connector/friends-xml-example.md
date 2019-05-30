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
# <a name="friends-xml-example"></a><span data-ttu-id="e7c33-105">好友 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e7c33-105">Friends XML example</span></span>

<span data-ttu-id="e7c33-106">本主题中的 XML 示例是在调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)方法后返回到 Outlook Social CONNECTOR (.osc) 的友元 xml 字符串。</span><span class="sxs-lookup"><span data-stu-id="e7c33-106">The XML example in this topic is a friend XML string returned to the Outlook Social Connector (OSC) after it calls the [ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) method.</span></span> <span data-ttu-id="e7c33-107">该示例显示了两个好友的**好友**XML, 每个好友由**person**元素分隔。</span><span class="sxs-lookup"><span data-stu-id="e7c33-107">The example shows the **friends** XML for two friends, each delimited by the **person** element.</span></span> <span data-ttu-id="e7c33-108">每个友元指定社交网络上**userID**元素的唯一值。</span><span class="sxs-lookup"><span data-stu-id="e7c33-108">Each friend specifies a unique value for the **userID** element on the social network.</span></span> 
  
<span data-ttu-id="e7c33-109">**友元**XML 的其余元素具有自解释的名称。</span><span class="sxs-lookup"><span data-stu-id="e7c33-109">The remaining elements of the **friends** XML have self-explanatory names.</span></span> <span data-ttu-id="e7c33-110">有关这些元素的详细说明, 请参阅[适用于好友的 XML](xml-for-friends.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c33-110">For detailed description of these elements, see [XML for Friends](xml-for-friends.md).</span></span> 
  
## <a name="xml-example"></a><span data-ttu-id="e7c33-111">XML 示例</span><span class="sxs-lookup"><span data-stu-id="e7c33-111">XML example</span></span>

<span data-ttu-id="e7c33-112">下面的示例展示了社交网络中两个人的**好友**XML。</span><span class="sxs-lookup"><span data-stu-id="e7c33-112">The following example shows the **friends** XML for two persons on the social network.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="e7c33-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7c33-113">See also</span></span>

- [<span data-ttu-id="e7c33-114">.OSC 提供程序 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e7c33-114">OSC Provider XML Examples</span></span>](osc-provider-xml-examples.md)  
- [<span data-ttu-id="e7c33-115">功能 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e7c33-115">Capabilities XML Example</span></span>](capabilities-xml-example.md) 
- [<span data-ttu-id="e7c33-116">活动源 XML 示例</span><span class="sxs-lookup"><span data-stu-id="e7c33-116">Activity Feed XML Example</span></span>](activity-feed-xml-example.md) 
- [<span data-ttu-id="e7c33-117">Outlook Social Connector 提供程序 XML 架构</span><span class="sxs-lookup"><span data-stu-id="e7c33-117">Outlook Social Connector Provider XML Schema</span></span>](outlook-social-connector-provider-xml-schema.md)

