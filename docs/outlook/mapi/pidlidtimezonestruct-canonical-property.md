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
# <a name="pidlidtimezonestruct-canonical-property"></a><span data-ttu-id="aed0f-103">PidLidTimeZoneStruct 规范属性</span><span class="sxs-lookup"><span data-stu-id="aed0f-103">PidLidTimeZoneStruct Canonical Property</span></span>

  
  
<span data-ttu-id="aed0f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aed0f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aed0f-105">包含映射到 [TZREG](https://msdn.microsoft.com/library/bb820983%28v=office.12%29.aspx) 结构的持久格式的流，该流描述用于定期约会或会议请求的开始时间和结束时间的时间。</span><span class="sxs-lookup"><span data-stu-id="aed0f-105">Contains a stream that maps to the persisted format of a [TZREG](https://msdn.microsoft.com/library/bb820983%28v=office.12%29.aspx) structure, which describes the time zone to be used for the start and end time of a recurring appointment or meeting request.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aed0f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="aed0f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="aed0f-107">dispidTimeZoneStruct</span><span class="sxs-lookup"><span data-stu-id="aed0f-107">dispidTimeZoneStruct</span></span>  <br/> |
|<span data-ttu-id="aed0f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="aed0f-108">Property set:</span></span>  <br/> |<span data-ttu-id="aed0f-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="aed0f-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="aed0f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="aed0f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="aed0f-111">0x00008233</span><span class="sxs-lookup"><span data-stu-id="aed0f-111">0x00008233</span></span>  <br/> |
|<span data-ttu-id="aed0f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="aed0f-112">Data type:</span></span>  <br/> |<span data-ttu-id="aed0f-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="aed0f-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="aed0f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="aed0f-114">Area:</span></span>  <br/> |<span data-ttu-id="aed0f-115">日历</span><span class="sxs-lookup"><span data-stu-id="aed0f-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aed0f-116">备注</span><span class="sxs-lookup"><span data-stu-id="aed0f-116">Remarks</span></span>

<span data-ttu-id="aed0f-117">Microsoft Office Outlook 2003、Outlook 的早期版本以及基于协作数据对象 (CDO) 1.21 的应用程序（用户尚未运行 Outlook 或 Exchange Server 提供的日历更新工具）将定期约会或会议请求的开始时间和结束时间存储为相对时间，并存储在 **dispidTimeZoneStruct** 中创建约会或会议请求的时区。</span><span class="sxs-lookup"><span data-stu-id="aed0f-117">Microsoft Office Outlook 2003, earlier versions of Outlook, and applications that are based on Collaboration Data Objects (CDO) 1.21 whose users have not run the calendar update tool provided by Outlook or Exchange Server store the start time and end time of a recurring appointment or meeting request as relative time, and store the time zone where the appointment or meeting request is created in **dispidTimeZoneStruct**.</span></span> <span data-ttu-id="aed0f-118">但是，此方案会忽略随着时间的推移，时区规则可能会更改，从而导致用户在更改规则之前安排的一些约会和会议，并且这些约会和会议在错误的时间发生。</span><span class="sxs-lookup"><span data-stu-id="aed0f-118">However, this scheme ignores that over time, time zone rules can change, resulting in some appointments and meetings that users scheduled before the rules changed and occur at incorrect times.</span></span> <span data-ttu-id="aed0f-119">未运行 Windows Vista 的用户和管理员或未启用自动更新的用户和管理员应该使用 Outlook 或 Exchange Server 提供的日历重基于工具来调整此类约会和会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="aed0f-119">Users and administrators who are not running Windows Vista or who do not have automatic updates turned on should use the calendar rebasing tools that are provided by Outlook or Exchange Server to adjust the time of such appointments and meeting requests.</span></span> <span data-ttu-id="aed0f-120">有关这些重基日历的日历重基工具和 API 详细信息，请参阅关于以编程方式为夏令时重基 [日历](https://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aed0f-120">For more information about these calendar rebasing tools and APIs that rebase calendars, see [About rebasing calendars programmatically for Daylight Saving Time](https://msdn.microsoft.com/library/38b342d9-ab10-04b6-5490-9a45f847a60f%28Office.15%29.aspx)</span></span>
  
<span data-ttu-id="aed0f-121">在分析从 **dispidTimeZoneStruct** 获取的流时，或在将 **TZREG** 结构持久化到流以提交到 **dispidTimeZoneStruct** 二进制属性时，请使用以下小尾格式。</span><span class="sxs-lookup"><span data-stu-id="aed0f-121">Use the following little-endian format when parsing a stream obtained from **dispidTimeZoneStruct**, or when persisting the **TZREG** structure to a stream to commit to the **dispidTimeZoneStruct** binary property.</span></span> 
  
```cpp
long        lBias;           // offset from GMT
long        lStandardBias;   // offset from bias during standard time
long        lDaylightBias;   // offset from bias during daylight time
WORD        wStandardYear;      // matches the stStandardDate's wYear member
SYSTEMTIME  stStandardDate;  // time to switch to standard time
WORD        wDaylightYear;      // matches the stDaylightDate's wYear field
SYSTEMTIME  stDaylightDate;  // time to switch to daylight time
```

<span data-ttu-id="aed0f-122">此属性在定期系列上设置为指定时区信息，并指定如何在本地时间与协调世界时 (UTC) 之间的时间字段。</span><span class="sxs-lookup"><span data-stu-id="aed0f-122">This property is set on a recurring series to specify time-zone information, and specifies how to convert time fields between local time and Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="aed0f-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="aed0f-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="aed0f-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="aed0f-124">Protocol specifications</span></span>

<span data-ttu-id="aed0f-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aed0f-125">[[MS-OXPROPS]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aed0f-126">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="aed0f-126">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="aed0f-127">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aed0f-127">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aed0f-128">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="aed0f-128">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="aed0f-129">头文件</span><span class="sxs-lookup"><span data-stu-id="aed0f-129">Header files</span></span>

<span data-ttu-id="aed0f-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aed0f-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="aed0f-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="aed0f-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aed0f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aed0f-132">See also</span></span>



[<span data-ttu-id="aed0f-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aed0f-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="aed0f-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="aed0f-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="aed0f-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="aed0f-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="aed0f-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="aed0f-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

