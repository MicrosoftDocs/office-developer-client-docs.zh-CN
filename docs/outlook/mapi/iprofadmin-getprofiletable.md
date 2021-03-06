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
ms.openlocfilehash: 2db7dba67e7b71df6921ecd97189255a0ef7823a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414642"
---
# <a name="iprofadmingetprofiletable"></a>IProfAdmin::GetProfileTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对配置文件表的访问权限，该表包含有关所有可用配置文件的信息。
  
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
  
> [out]指向指向配置文件表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索配置文件表。
    
## <a name="remarks"></a>备注

**IProfAdmin：：GetProfileTable** 方法提供对配置文件表的访问，该表包含每个可用配置文件的一行。 每行中只有两列：配置文件的显示名称和一个指示配置文件是否是默认配置文件的标志。 
  
配置文件表中不包含已删除或已在使用中但标记为删除的配置文件。 配置文件表是静态的;后续的添加和删除配置文件不会反映在表中。 
  
如果不存在配置文件 **，GetProfileTable** 将返回包含零行的表。 
  
有关配置文件表的信息，请参阅配置文件 [表](profile-tables.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnShowProfiles  <br/> |MFCMAPI 使用 **IProfAdmin：：GetProfileTable** 方法获取要显示在新对话框中的配置文件表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

