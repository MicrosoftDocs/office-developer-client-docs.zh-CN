---
title: PidLidTimeZoneStruct 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTimeZoneStruct
api_type:
- COM
ms.assetid: 2acf0036-2f3e-4f90-8614-7aa667860f74
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a1a96cdb3aed03b9621097f1ef858a09391c0693
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777115"
---
# <a name="pidlidtimezonestruct-canonical-property"></a><span data-ttu-id="2ccab-103">PidLidTimeZoneStruct 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ccab-103">PidLidTimeZoneStruct Canonical Property</span></span>

  
  
<span data-ttu-id="2ccab-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2ccab-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2ccab-105">包含映射到[TZREG](http://msdn.microsoft.com/en-us/library/bb820983%28v=office.12%29.aspx)结构，其中介绍了用于定期约会或会议请求的开始和结束时间的时区的持久化格式的流。</span><span class="sxs-lookup"><span data-stu-id="2ccab-105">Contains a stream that maps to the persisted format of a [TZREG](http://msdn.microsoft.com/en-us/library/bb820983%28v=office.12%29.aspx) structure, which describes the time zone to be used for the start and end time of a recurring appointment or meeting request.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2ccab-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="2ccab-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ccab-107">dispidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="2ccab-107">dispidTimeZoneStruct</span></span>  <br/> |
|<span data-ttu-id="2ccab-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2ccab-108">Property set:</span></span>  <br/> |<span data-ttu-id="2ccab-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="2ccab-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="2ccab-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2ccab-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2ccab-111">0x00008233</span><span class="sxs-lookup"><span data-stu-id="2ccab-111">0x00008233</span></span>  <br/> |
|<span data-ttu-id="2ccab-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ccab-112">Data type:</span></span>  <br/> |<span data-ttu-id="2ccab-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2ccab-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2ccab-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2ccab-114">Area:</span></span>  <br/> |<span data-ttu-id="2ccab-115">日历</span><span class="sxs-lookup"><span data-stu-id="2ccab-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ccab-116">备注</span><span class="sxs-lookup"><span data-stu-id="2ccab-116">Remarks</span></span>

<span data-ttu-id="2ccab-117">Microsoft Office Outlook 2003，早期版本的 Outlook 和应用程序上协作数据对象 (CDO) 1.21 基于其用户还未运行 Outlook 或 Exchange Server 提供的日历更新工具存储的开始时间和结束时间定期约会或会议请求为相对的时间，并将存储其中**dispidTimeZoneStruct**中创建约会或会议请求的时区。</span><span class="sxs-lookup"><span data-stu-id="2ccab-117">Microsoft Office Outlook 2003, earlier versions of Outlook, and applications that are based on Collaboration Data Objects (CDO) 1.21 whose users have not run the calendar update tool provided by Outlook or Exchange Server store the start time and end time of a recurring appointment or meeting request as relative time, and store the time zone where the appointment or meeting request is created in **dispidTimeZoneStruct**.</span></span> <span data-ttu-id="2ccab-118">但是，将忽略此方案，随时间推移，时区规则可以更改，导致某些约会和会议安排规则更改，并在不正确的时间之前该用户。</span><span class="sxs-lookup"><span data-stu-id="2ccab-118">However, this scheme ignores that over time, time zone rules can change, resulting in some appointments and meetings that users scheduled before the rules changed and occur at incorrect times.</span></span> <span data-ttu-id="2ccab-119">用户和用户未运行 Windows Vista 或那些没有开启自动更新的管理员应使用定位提供 Outlook 或 Exchange Server 调整此类约会和会议请求的时间的工具的日历。</span><span class="sxs-lookup"><span data-stu-id="2ccab-119">Users and administrators who are not running Windows Vista or who do not have automatic updates turned on should use the calendar rebasing tools that are provided by Outlook or Exchange Server to adjust the time of such appointments and meeting requests.</span></span> <span data-ttu-id="2ccab-120">有关这些日历调整工具和重定日历基值的 Api 的详细信息，请参阅[关于编程方式为夏时制调整日历](http://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ccab-120">For more information about these calendar rebasing tools and APIs that rebase calendars, see [About rebasing calendars programmatically for Daylight Saving Time](http://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span></span>
  
<span data-ttu-id="2ccab-121">使用以下-little-endian 格式时分析流持久化到流**TZREG**结构时所获得从**dispidTimeZoneStruct**，或提交到**dispidTimeZoneStruct**二进制属性。</span><span class="sxs-lookup"><span data-stu-id="2ccab-121">Use the following little-endian format when parsing a stream obtained from **dispidTimeZoneStruct**, or when persisting the **TZREG** structure to a stream to commit to the **dispidTimeZoneStruct** binary property.</span></span> 
  
```cpp
long        lBias;           // offset from GMT
long        lStandardBias;   // offset from bias during standard time
long        lDaylightBias;   // offset from bias during daylight time
WORD        wStandardYear;      // matches the stStandardDate's wYear member
SYSTEMTIME  stStandardDate;  // time to switch to standard time
WORD        wDaylightYear;      // matches the stDaylightDate's wYear field
SYSTEMTIME  stDaylightDate;  // time to switch to daylight time
```

<span data-ttu-id="2ccab-122">此属性设置为定期系列上指定时区信息，并指定如何转换本地时间与协调世界时 (UTC) 之间的时间字段。</span><span class="sxs-lookup"><span data-stu-id="2ccab-122">This property is set on a recurring series to specify time-zone information, and specifies how to convert time fields between local time and Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2ccab-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ccab-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2ccab-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="2ccab-124">Protocol specifications</span></span>

<span data-ttu-id="2ccab-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ccab-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ccab-126">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2ccab-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2ccab-127">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ccab-127">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2ccab-128">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="2ccab-128">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2ccab-129">头文件</span><span class="sxs-lookup"><span data-stu-id="2ccab-129">Header files</span></span>

<span data-ttu-id="2ccab-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ccab-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ccab-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ccab-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ccab-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ccab-132">See also</span></span>



[<span data-ttu-id="2ccab-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ccab-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ccab-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ccab-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ccab-135">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ccab-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ccab-136">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ccab-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

