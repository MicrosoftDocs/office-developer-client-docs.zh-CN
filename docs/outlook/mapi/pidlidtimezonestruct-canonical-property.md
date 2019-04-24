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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9c2a1bbf519379c1735c489c2dcd3fcfb395a60
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346373"
---
# <a name="pidlidtimezonestruct-canonical-property"></a><span data-ttu-id="a94bb-103">PidLidTimeZoneStruct 规范属性</span><span class="sxs-lookup"><span data-stu-id="a94bb-103">PidLidTimeZoneStruct Canonical Property</span></span>

  
  
<span data-ttu-id="a94bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a94bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a94bb-105">包含映射到[TZREG](https://msdn.microsoft.com/library/bb820983%28v=office.12%29.aspx)结构的保留格式的流, 该格式描述要用于定期约会或会议请求的开始和结束时间的时区。</span><span class="sxs-lookup"><span data-stu-id="a94bb-105">Contains a stream that maps to the persisted format of a [TZREG](https://msdn.microsoft.com/library/bb820983%28v=office.12%29.aspx) structure, which describes the time zone to be used for the start and end time of a recurring appointment or meeting request.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a94bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a94bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a94bb-107">dispidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="a94bb-107">dispidTimeZoneStruct</span></span>  <br/> |
|<span data-ttu-id="a94bb-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="a94bb-108">Property set:</span></span>  <br/> |<span data-ttu-id="a94bb-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="a94bb-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="a94bb-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="a94bb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a94bb-111">0x00008233</span><span class="sxs-lookup"><span data-stu-id="a94bb-111">0x00008233</span></span>  <br/> |
|<span data-ttu-id="a94bb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a94bb-112">Data type:</span></span>  <br/> |<span data-ttu-id="a94bb-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a94bb-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a94bb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a94bb-114">Area:</span></span>  <br/> |<span data-ttu-id="a94bb-115">日历</span><span class="sxs-lookup"><span data-stu-id="a94bb-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a94bb-116">注解</span><span class="sxs-lookup"><span data-stu-id="a94bb-116">Remarks</span></span>

<span data-ttu-id="a94bb-117">Microsoft Office Outlook 2003, 早期版本的 Outlook, 以及基于协作数据对象 (CDO) 1.21 的应用程序, 其用户未运行 Outlook 或 Exchange Server 存储提供的日历更新工具的开始时间和结束时间相对于相对时间的定期约会或会议请求, 并存储在**dispidTimeZoneStruct**中创建约会或会议请求的时区。</span><span class="sxs-lookup"><span data-stu-id="a94bb-117">Microsoft Office Outlook 2003, earlier versions of Outlook, and applications that are based on Collaboration Data Objects (CDO) 1.21 whose users have not run the calendar update tool provided by Outlook or Exchange Server store the start time and end time of a recurring appointment or meeting request as relative time, and store the time zone where the appointment or meeting request is created in **dispidTimeZoneStruct**.</span></span> <span data-ttu-id="a94bb-118">但是, 这种方案将忽略这一段时间, 时区规则可能会更改, 从而导致在规则发生更改并在不正确的时间发生之前计划用户的一些约会和会议。</span><span class="sxs-lookup"><span data-stu-id="a94bb-118">However, this scheme ignores that over time, time zone rules can change, resulting in some appointments and meetings that users scheduled before the rules changed and occur at incorrect times.</span></span> <span data-ttu-id="a94bb-119">未运行 Windows Vista 或未启用自动更新的用户和管理员应使用 Outlook 或 Exchange Server 提供的日历重定工具来调整此类约会和会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="a94bb-119">Users and administrators who are not running Windows Vista or who do not have automatic updates turned on should use the calendar rebasing tools that are provided by Outlook or Exchange Server to adjust the time of such appointments and meeting requests.</span></span> <span data-ttu-id="a94bb-120">有关可变基日历的这些日历重定工具和 api 的详细信息, 请参阅 "[关于以编程方式重定日历" 以实现夏时制](https://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a94bb-120">For more information about these calendar rebasing tools and APIs that rebase calendars, see [About rebasing calendars programmatically for Daylight Saving Time](https://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span></span>
  
<span data-ttu-id="a94bb-121">在分析从**dispidTimeZoneStruct**获取的流时, 或者在将**TZREG**结构保留为要提交到**dispidTimeZoneStruct**二进制属性的流时, 使用以下小字节格式的格式。</span><span class="sxs-lookup"><span data-stu-id="a94bb-121">Use the following little-endian format when parsing a stream obtained from **dispidTimeZoneStruct**, or when persisting the **TZREG** structure to a stream to commit to the **dispidTimeZoneStruct** binary property.</span></span> 
  
```cpp
long        lBias;           // offset from GMT
long        lStandardBias;   // offset from bias during standard time
long        lDaylightBias;   // offset from bias during daylight time
WORD        wStandardYear;      // matches the stStandardDate's wYear member
SYSTEMTIME  stStandardDate;  // time to switch to standard time
WORD        wDaylightYear;      // matches the stDaylightDate's wYear field
SYSTEMTIME  stDaylightDate;  // time to switch to daylight time
```

<span data-ttu-id="a94bb-122">此属性在定期系列上设置, 以指定时区信息, 并指定如何在本地时间与协调通用时间 (UTC) 之间转换时间字段。</span><span class="sxs-lookup"><span data-stu-id="a94bb-122">This property is set on a recurring series to specify time-zone information, and specifies how to convert time fields between local time and Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a94bb-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="a94bb-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a94bb-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="a94bb-124">Protocol specifications</span></span>

<span data-ttu-id="a94bb-125">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a94bb-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a94bb-126">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a94bb-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a94bb-127">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a94bb-127">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a94bb-128">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a94bb-128">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a94bb-129">头文件</span><span class="sxs-lookup"><span data-stu-id="a94bb-129">Header files</span></span>

<span data-ttu-id="a94bb-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a94bb-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="a94bb-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a94bb-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a94bb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a94bb-132">See also</span></span>



[<span data-ttu-id="a94bb-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a94bb-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a94bb-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a94bb-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a94bb-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a94bb-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a94bb-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a94bb-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

