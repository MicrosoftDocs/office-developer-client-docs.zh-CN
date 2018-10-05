---
title: （Outlook 导出的 Api） 的常量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 7590a30e-3fd8-7ae3-f077-c80f6cc21d7b
description: 本主题包含常量定义的 Outlook 导出 Api。
ms.openlocfilehash: 65181932b858da1b32c3fbe5fd0bd7e92ca8dc9f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386073"
---
# <a name="constants-outlook-exported-apis"></a>（Outlook 导出的 Api） 的常量

本主题包含常量定义的 Outlook 导出 Api。
  
## <a name="definitions-for-time-zone-support"></a>定义时区的支持

```cpp
const ULONG TZ_MAX_RULES                    = 0x00000001;  
const BYTE  TZ_BIN_VERSION_MAJOR            = 0x02;  
const BYTE  TZ_BIN_VERSION_MINOR            = 0x01; 
const WORD  TZRULE_FLAG_RECUR_CURRENT_TZREG = 0x0001; 
const WORD  TZRULE_FLAG_EFFECTIVE_TZREG     = 0x0002; 
const WORD  TZDEFINITION_FLAG_VALID_KEYNAME = 0x0002;
```

## <a name="definitions-for-category-support"></a>为类别定义支持

|**常量**|**定义**|
|:-----|:-----|
|PCAFSIF_MSGEID_IS_SEARCH_KEY  <br/> |0x00000001  <br/> |
   
## <a name="miscellaneous-dispatch-identifiers"></a>Miscellaneous 调度标识符

Outlook 公开以下调度标识符 (dispid)，以便开发人员可以使用[idispatch:: Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)访问的相应属性或方法，或收听对应的事件。 
  
|**关联的常量**|**Dispid 值**|**说明**|**适用的接口**|
|:-----|:-----|:-----|:-----|
|**dispidFDirty** <br/> |0xF024  <br/> |用于调用以验证项目是否已修改但未保存项目上的相应属性。  <br/> |项目级对象  <br/> |
|**dispidShowSenderPhoto** <br/> |0xF0D0  <br/> |用于调用以指定是否显示联系人的图片，基于给定的参数的资源管理器或检查器的对应方法。  <br/> |资源管理器或检查器  <br/> |
|**dispidBeforePrint** <br/> |0xFC8E  <br/> |用于处理来自**idispatch:: Invoke**函数打印操作前触发的事件。  <br/> |应用程序  <br/> |
|**dispidEventReadComplete** <br/> |0xFC8F  <br/> |用于处理从**idispatch:: Invoke**函数 Outlook 已完成读取项目的属性时触发的事件。  <br/> |项目级对象  <br/> |
   
## <a name="see-also"></a>另请参阅

- [Outlook 导出的 API](outlook-exported-apis.md)
- [关于 Outlook 导出的 API](about-apis-exported-by-outlook.md)
- [确定某个 Outlook 项目是否已修改但未保存（Outlook 辅助参考）](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
- [指定是否要在 Outlook（Outlook 辅助参考）中显示联系人的图片](https://msdn.microsoft.com/library/office/gg262879.aspx)
- [可用的事件和其 dispid （Outlook 导出的 Api）](available-events-and-their-dispids-outlook-exported-apis.md)

