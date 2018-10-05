---
title: 从约会中读取时区属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ba1b9425-6c16-cab2-da0a-a21734118098
description: 本主题显示一个函数，ReadTimeZones，调用 BinToTZDEFINITION 以及 BinToTZREG，所在的时区属性，PidLidAppointmentTimeZoneDefinitionStartDisplay 和 PidLidTimeZoneStruct，读取从约会的两个函数。
ms.openlocfilehash: 67755ba49c5572005c6138e34329491148a199a1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396034"
---
# <a name="read-time-zone-properties-from-an-appointment"></a><span data-ttu-id="50ea4-103">从约会中读取时区属性</span><span class="sxs-lookup"><span data-stu-id="50ea4-103">Read time zone properties from an appointment</span></span>

<span data-ttu-id="50ea4-104">本主题显示一个函数，`ReadTimeZones`的呼叫的两个功能，`BinToTZDEFINITION`和`BinToTZREG`，以所在的时区属性， [PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)和[PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)，读取约会。</span><span class="sxs-lookup"><span data-stu-id="50ea4-104">This topic shows a function,  `ReadTimeZones`, that calls the two functions,  `BinToTZDEFINITION` and  `BinToTZREG`, to read the time zone properties, [PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx) and [PidLidTimeZoneStruct](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx), from an appointment.</span></span>
  
<span data-ttu-id="50ea4-105">**PidLidAppointmentTimeZoneDefinitionStartDisplay**包含映射到的[TZDEFINITION](tzdefinition.md)结构持久化格式的流并且**PidLidTimeZoneStruct**包含映射到的[TZREG](tzreg.md)持久化格式的流结构。</span><span class="sxs-lookup"><span data-stu-id="50ea4-105">**PidLidAppointmentTimeZoneDefinitionStartDisplay** contains a stream that maps to the persisted format of a [TZDEFINITION](tzdefinition.md) structure, and **PidLidTimeZoneStruct** contains a stream that maps to the persisted format of a [TZREG](tzreg.md) structure.</span></span> <span data-ttu-id="50ea4-106">若要获取的确切的**TZDEFINITION**和**TZREG**结构`BinToTZDEFINITION`和`BinToTZREG`用于适当地分析流这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="50ea4-106">To obtain the exact **TZDEFINITION** and **TZREG** structures,  `BinToTZDEFINITION` and  `BinToTZREG` are used to parse the stream values of these properties appropriately.</span></span> <span data-ttu-id="50ea4-107">分别在[分析 stream 从二进制属性以读取 TZDEFINITION 结构](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)并[分析从二进制属性以读取 TZREG 结构流](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)，请中定义了这两个函数。</span><span class="sxs-lookup"><span data-stu-id="50ea4-107">These two functions are defined in [Parse a stream from a binary property to read the TZDEFINITION structure](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md) and [Parse a stream from a binary property to read the TZREG structure](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md), respectively.</span></span> 
  
```cpp
void ReadTimeZones(LPMAPIPROP lpAppointment) 
{ 
    HRESULT hRes = S_OK; 
    LPSPropTagArray lpNamedPropTags = NULL; 
    MAPINAMEID NamedID[2] = {0}; 
    LPMAPINAMEID lpNamedID[2]; 
    lpNamedID[0] = &amp;NamedID[0]; 
    lpNamedID[1] = &amp;NamedID[1]; 
    NamedID[0].lpguid = (LPGUID)&amp;PSETID_Appointment; 
    NamedID[0].ulKind = MNID_ID; 
    NamedID[0].Kind.lID = dispidTimeZoneStruct; 
    NamedID[1].lpguid = (LPGUID)&amp;PSETID_Appointment; 
    NamedID[1].ulKind = MNID_ID; 
    NamedID[1].Kind.lID = dispidApptTZDefStartDisplay; 
    hRes = lpAppointment->GetIDsFromNames( 
        2, 
        lpNamedID, 
        NULL, 
        &amp;lpNamedPropTags); 
    if (SUCCEEDED(hRes) &amp;&amp; lpNamedPropTags) 
    { 
        SizedSPropTagArray(2,sptaTzProps) = {2, 
            CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[0],PT_BINARY), 
            CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[1],PT_BINARY), 
        }; 
        LPSPropValue lpProps = NULL; 
        ULONG cProps = 0; 
        hRes = lpAppointment->GetProps( 
            (LPSPropTagArray)&amp;sptaTzProps, 
            NULL, 
            &amp;cProps, 
            &amp;lpProps); 
        if (SUCCEEDED(hRes) &amp;&amp; 2 == cProps &amp;&amp; lpProps) 
        { 
            if (PT_BINARY == PROP_TYPE(lpProps[0].ulPropTag)) 
            { 
                TZREG* ptzReg = BinToTZREG(lpProps[0].Value.bin.cb,lpProps[0].Value.bin.lpb); 
                // TODO: Do whatever is necessary with ptzReg. 
                delete ptzReg; 
            } 
            if (PT_BINARY == PROP_TYPE(lpProps[1].ulPropTag)) 
            { 
                TZDEFINITION* ptzDef = BinToTZDEFINITION(lpProps[1].Value.bin.cb,lpProps[1].Value.bin.lpb); 
                // TODO: Do whatever is necessary with ptzDef. 
                delete[] ptzDef; 
            } 
           } 
        MAPIFreeBuffer(lpProps); 
    } 
    MAPIFreeBuffer(lpNamedPropTags); 
}
```

## <a name="see-also"></a><span data-ttu-id="50ea4-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50ea4-108">See also</span></span>

- [<span data-ttu-id="50ea4-109">有关重定基址日历以编程方式为夏时制</span><span class="sxs-lookup"><span data-stu-id="50ea4-109">About rebasing calendars programmatically for Daylight Saving Time</span></span>](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

