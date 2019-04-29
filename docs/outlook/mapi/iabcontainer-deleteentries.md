---
title: IABContainerDeleteEntries
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.DeleteEntries
api_type:
- COM
ms.assetid: 70a24811-0c41-4b44-8c63-7ef807bc9051
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e3b238129e55e03da33ef3af75ecce7e73fbad03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425594"
---
# <a name="iabcontainerdeleteentries"></a>IABContainer::DeleteEntries

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除一个或多个条目, 通常是邮件用户、通讯组列表或其他容器。
  
```cpp
HRESULT DeleteEntries(
  LPENTRYLIST lpEntries,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpEntries_
  
> 实时指向[ENTRYLIST](entrylist.md)结构数组的指针, 该数组包含表示要删除的项的条目标识符。 
    
 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除指定的条目。 
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功, 但无法删除一个或多个条目。 返回此值时, 应以成功的方式处理该调用。 若要测试此值, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|Abdlg  <br/> |CabDlg:: OnDeleteSelectedItem  <br/> |MFCMAPI 使用**DeleteEntries**方法从通讯簿容器中删除特定的条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

