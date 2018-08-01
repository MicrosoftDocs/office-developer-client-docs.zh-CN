---
title: IProfAdminGetProfileTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetProfileTable
api_type:
- COM
ms.assetid: cebccd2d-8215-486e-9964-7fc42412cec6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c942bdbf27590dde04b84970e345f265bc645045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776008"
---
# <a name="iprofadmingetprofiletable"></a>IProfAdmin::GetProfileTable

  
  
**适用于**： Outlook 
  
提供对配置文件表中，一个表，包含有关所有可用的配置文件信息的访问。
  
```cpp
HRESULT GetProfileTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]始终为 NULL。
    
 _lppTable_
  
> [输出]指向配置文件表格的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索配置文件表。
    
## <a name="remarks"></a>说明

**IProfAdmin::GetProfileTable**方法提供了对配置文件表，其中包含一行，每个可用的配置文件的访问。 在每行中有只有两个列： 配置文件的显示名称和一个指示的配置文件是否是默认的标志。 
  
配置文件已被删除，或的仍在使用，但已标记为删除，不包括在配置文件表。 配置文件表是静态;后续的添加和配置文件的删除操作不会反映表中。 
  
如果没有配置文件存在，则**GetProfileTable**将返回具有零个行的表。 
  
有关配置文件表的详细信息，请参阅[配置文件表](profile-tables.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnShowProfiles  <br/> |MFCMAPI 使用**IProfAdmin::GetProfileTable**方法来获取要在新的对话框中显示的配置文件表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

