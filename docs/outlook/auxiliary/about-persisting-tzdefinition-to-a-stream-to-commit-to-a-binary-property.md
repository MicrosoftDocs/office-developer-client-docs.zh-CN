---
title: 关于将 TZDEFINITION 保存到流以提交到二进制属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 0dec535d-d48f-39a5-97d5-0bd109134b3b
description: 时区属性 PidLidAppointmentTimeZoneDefinitionEndDisplay、PidLidAppointmentTimeZoneDefinitionRecur 和 PidLidAppointmentTimeZoneDefinitionStartDisplay 是二进制命名属性，其中每个属性都包含映射到 TZDEFINITION 结构的持久格式的流。
ms.openlocfilehash: f94b751a55aa852c962eebe5d46968e9e622e315
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316973"
---
# <a name="about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property"></a><span data-ttu-id="51ab3-103">关于将 TZDEFINITION 保存到流以提交到二进制属性</span><span class="sxs-lookup"><span data-stu-id="51ab3-103">About persisting TZDEFINITION to a stream to commit to a binary property</span></span>

<span data-ttu-id="51ab3-104">时区属性[PidLidAppointmentTimeZoneDefinitionEndDisplay、PidLidAppointmentTimeZoneDefinitionRecur](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)和[PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)是二进制命名属性，其中每个属性都包含映射到[TZDEFINITION](tzdefinition.md)结构的持久格式的流。 [](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="51ab3-104">The time zone properties, [PidLidAppointmentTimeZoneDefinitionEndDisplay](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx), [PidLidAppointmentTimeZoneDefinitionRecur](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx), and [PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx) are binary named properties, each of which contains a stream that maps to the persisted format of a [TZDEFINITION](tzdefinition.md) structure.</span></span> 
  
<span data-ttu-id="51ab3-105">本主题介绍将 **TZDEFINITION** 持久化到流以提交到三个二进制属性之一时可以使用的一种小尾格式。</span><span class="sxs-lookup"><span data-stu-id="51ab3-105">This topic describes a little endian format that can be used when persisting **TZDEFINITION** to a stream to commit to one of three binary properties.</span></span> <span data-ttu-id="51ab3-106">在分析器中使用相同的尾数格式解释从这些属性之一获取的流值。</span><span class="sxs-lookup"><span data-stu-id="51ab3-106">Use the same endian format in a parser to interpret a stream value obtained from one of these properties.</span></span> 
  
```cpp
BYTE  bMajorVersion;    // breaking change
BYTE  bMinorVersion;    // extensibility
WORD  cbHeader;         // size of following data until TZREG sub structure
WORD  wFlags;
if (TZDEFINITION_FLAG_VALID_GUID)
   GUID  guid;                // guid
if (TZDEFINITION_FLAG_VALID_KEYNAME)     
    WORD   cchKeyName;        // does not include null char
    WCHAR  rgchKeyName;       // not null terminated
    WORD  cRules;             // number of rules
// for each rule
   BYTE        bMajorVersion;         // breaking change
   BYTE        bMinorVersion;         // extensibility
   WORD        cbRule;                // size of following data
   WORD        wFlags;                // flags
   SYSTEMTIME  stStart;               // GMT when this rule starts
// Following are the fields of the TZREG sub structure
   long        lBias;                // offset from GMT
   long        lStandardBias;        // offset from bias during standard time
   long        lDaylightBias;        // offset from bias during daylight time
   SYSTEMTIME  stStandardDate;       // time to switch to standard time
   SYSTEMTIME  stDaylightDate;       // time to switch to daylight time
```

<span data-ttu-id="51ab3-107">主版本号用于进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="51ab3-107">The major version number is used to make a breaking change.</span></span> <span data-ttu-id="51ab3-108">不熟悉主版本号的客户端应该将该属性视为不存在。</span><span class="sxs-lookup"><span data-stu-id="51ab3-108">Clients that are unfamiliar with the major version number should treat the property as if it is not there.</span></span> <span data-ttu-id="51ab3-109">编写结构的客户端应指定常量 **TZ_BIN_VERSION_MAJOR。**</span><span class="sxs-lookup"><span data-stu-id="51ab3-109">Clients writing the structure should specify the constant **TZ_BIN_VERSION_MAJOR**.</span></span> 
  
<span data-ttu-id="51ab3-110">次要版本号用于扩展性。</span><span class="sxs-lookup"><span data-stu-id="51ab3-110">The minor version number is used for extensibility.</span></span> <span data-ttu-id="51ab3-111">不熟悉次要版本号的客户端应读取他们理解的数据，并跳过可能附加到每个规则或整个流的数据。</span><span class="sxs-lookup"><span data-stu-id="51ab3-111">Clients that are unfamiliar with the minor version number should read the data that they understand, and skip over the data that might be appended to each rule or to the overall stream.</span></span> <span data-ttu-id="51ab3-112">编写结构的客户端应指定常量 **TZ_BIN_VERSION_MINOR。**</span><span class="sxs-lookup"><span data-stu-id="51ab3-112">Clients writing the structure should specify the constant **TZ_BIN_VERSION_MINOR**.</span></span> 
  
<span data-ttu-id="51ab3-113">如果分析程序无法理解标头的主要版本，则它不应读取结构的其余部分，并像缺少数据一样运行。</span><span class="sxs-lookup"><span data-stu-id="51ab3-113">If a parser does not understand the major version of the header, it should not read the rest of the structure and behave as if the data is missing.</span></span> <span data-ttu-id="51ab3-114">如果分析程序无法理解标头的次要版本，则它应当使用 **cbHeader** 忽略它无法理解的部分，并提前读取它理解的流部分。</span><span class="sxs-lookup"><span data-stu-id="51ab3-114">If a parser does not understand the minor version of the header, it should use **cbHeader** to ignore the portions that it does not understand and advance to read the portions of the stream that it understands.</span></span> 
  
<span data-ttu-id="51ab3-115">**wFlags 的值** 始终为 **TZDEFINITION_FLAG_VALID_KEYNAME**。</span><span class="sxs-lookup"><span data-stu-id="51ab3-115">The value of **wFlags** is always **TZDEFINITION_FLAG_VALID_KEYNAME**.</span></span> <span data-ttu-id="51ab3-116">键名称的最大大小为 **MAX_PATH**。</span><span class="sxs-lookup"><span data-stu-id="51ab3-116">The key name has a maximum size of **MAX_PATH**.</span></span> 
  
<span data-ttu-id="51ab3-117">如果分析程序无法识别规则的主要版本，客户端应忽略该规则，并使用 **cbRule** 前进到下一个规则。</span><span class="sxs-lookup"><span data-stu-id="51ab3-117">If a parser does not recognize the major version of a rule, the client should ignore the rule, and use **cbRule** to advance to the next rule.</span></span> <span data-ttu-id="51ab3-118">如果分析程序无法识别规则的次要版本，则客户端只应分析它理解的规则部分。</span><span class="sxs-lookup"><span data-stu-id="51ab3-118">If a parser does not recognize the minor version of a rule, the client should only parse the parts of the rule that it understands.</span></span> 
  
<span data-ttu-id="51ab3-119">将 **TZDEFINITION** 结构持久化到流时，分析程序不应尝试编写它无法理解的任何信息。</span><span class="sxs-lookup"><span data-stu-id="51ab3-119">When persisting a **TZDEFINITION** structure to a stream, a parser should not try to write any information that it does not understand.</span></span> 
  
<span data-ttu-id="51ab3-120">最大规则数为 1024。</span><span class="sxs-lookup"><span data-stu-id="51ab3-120">The maximum number of rules is 1024.</span></span>
  
<span data-ttu-id="51ab3-121">请注意， [此处保留 TZREG](tzreg.md) 结构的方式与单独保留时不同，因此不能使用相同的代码进行分析。</span><span class="sxs-lookup"><span data-stu-id="51ab3-121">Note that the [TZREG](tzreg.md) structure is persisted here differently than when persisted alone, so the same code cannot be used to parse it.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="51ab3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51ab3-122">See also</span></span>

- [<span data-ttu-id="51ab3-123">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="51ab3-123">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="51ab3-124">分析二进制属性读取 TZDEFINITION 结构的流</span><span class="sxs-lookup"><span data-stu-id="51ab3-124">Parse a stream from a binary property to read the TZDEFINITION structure</span></span>](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [<span data-ttu-id="51ab3-125">从约会中读取时区属性</span><span class="sxs-lookup"><span data-stu-id="51ab3-125">Read time zone properties from an appointment</span></span>](how-to-read-time-zone-properties-from-an-appointment.md)

