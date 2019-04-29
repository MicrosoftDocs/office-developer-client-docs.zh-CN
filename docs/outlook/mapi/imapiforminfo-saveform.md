---
title: IMAPIFormInfoSaveForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.SaveForm
api_type:
- COM
ms.assetid: 18a10f14-0795-4d4d-b590-f4cef4f2902a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 391ea3ef4f44db2a9d007241232f58db27647ba2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428744"
---
# <a name="imapiforminfosaveform"></a>IMAPIFormInfo::SaveForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在配置文件中保存特定窗体的说明。
  
```cpp
HRESULT SaveForm(
  LPCSTR szFileName
);
```

## <a name="parameters"></a>参数

 _szFileName_
  
> 实时一个字符串, 用于在保存其说明的位置命名表单的说明邮件文件。 此文件名必须具有扩展名 fdm。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_EXTENDED_ERROR 
  
> 无法写入配置文件。 若要获取与错误相关联的[MAPIERROR](mapierror.md)结构, 请调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法。 
    
MAPI_E_NO_SUPPORT 
  
> **SaveForm**可能被称为将表单保存在本地表单容器中。 本地表单容器上不支持**SaveForm** 。 
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormInfo:: SaveForm**方法将当前表单的说明保存在具有给定文件名的文件中。 **SaveForm**创建配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过在表单库提供程序显示的对话框中从表单描述符消息列表中进行选择来重新安装表单。 推荐的窗体描述符消息扩展名为 fdm。
  
如果**SaveForm**返回 MAPI_E_EXTENDED_ERROR, 则调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法, 然后检查返回的**MAPIERROR**结构以确定导致错误的条件。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

