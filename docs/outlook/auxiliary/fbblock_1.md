---
title: FBBlock_1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: da67171d-d25f-3424-1409-33189ac63a12
description: 定义忙/闲数据块。 这是由的约会或会议请求日历的项目。
ms.openlocfilehash: 93418e3777e9d9f0a016822ea5897b8fccc37ac3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774174"
---
# <a name="fbblock1"></a>FBBlock_1

定义忙/闲数据块。 这是由的约会或会议请求日历的项目。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct  tagFBBlock_1 
    { 
    long m_tmStart; 
    long m_tmEnd; 
    FBStatus m_fbstatus; 
    }FBBlock_1; 

```

## <a name="members"></a>Members

_m_tmStart_
  
> 块，表示相对时间的开始时间。 有关详细信息，请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。
    
_m_tmEnd_
  
> 块，表示相对时间的结束时间。
    
_m_fbStatus_
  
> 此块，指示用户是否-外出、 忙碌、 暂定、 或免费、 _m_tmStart_和_m_tmEnd_之间的时段内的忙/闲状态。
    
## <a name="see-also"></a>另请参阅

- [FBStatus](fbstatus.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

