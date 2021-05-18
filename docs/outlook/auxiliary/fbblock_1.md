---
title: FBBlock_1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: da67171d-d25f-3424-1409-33189ac63a12
description: 定义一个忙/闲数据块。 这是日历上的一个项目，由约会或会议请求表示。
ms.openlocfilehash: 60d2ff50081a8950a397df6f2f6bbfd37d3bdb61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413197"
---
# <a name="fbblock_1"></a>FBBlock_1

定义一个忙/闲数据块。 这是日历上的一个项目，由约会或会议请求表示。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct  tagFBBlock_1 
    { 
    long m_tmStart; 
    long m_tmEnd; 
    FBStatus m_fbstatus; 
    }FBBlock_1; 

```

## <a name="members"></a>成员

_m_tmStart_
  
> 块的开始时间，以相对时间表示。 有关详细信息，请参阅使用 [相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。
    
_m_tmEnd_
  
> 块的结束时间，以相对时间表示。
    
_m_fbStatus_
  
> 此块的忙/闲状态，指示用户在 m_tmStart 和 m_tmEnd 之间的时间段是外出、忙碌  _、_ 暂定还是  _空闲_。
    
## <a name="see-also"></a>另请参阅

- [FBStatus](fbstatus.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)
- [使用访问忙/闲数据的相对时间](how-to-use-relative-time-to-access-free-busy-data.md)

