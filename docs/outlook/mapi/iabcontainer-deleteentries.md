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
ms.openlocfilehash: c744407790fecde6b6d89dff669ea4db07ce7701
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775199"
---
# <a name="iabcontainerdeleteentries"></a>IABContainer::DeleteEntries

  
  
**适用于**： Outlook 
  
删除一个或多个条目，通常消息的用户、 通讯组列表或其他容器。
  
```cpp
HRESULT DeleteEntries(
  LPENTRYLIST lpEntries,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpEntries_
  
> [in]一个指向包含代表要删除的条目的项标识符的[ENTRYLIST](entrylist.md)结构的数组。 
    
 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除指定的项。 
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但无法删除一个或多个条目。 返回此值时，应处理呼叫为成功。 若要测试此值，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|Abdlg.cpp  <br/> |CabDlg::OnDeleteSelectedItem  <br/> |MFCMAPI 使用**DeleteEntries**方法从通讯簿容器中删除特定的条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

