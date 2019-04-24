---
title: IMAPIFormMgrPrepareForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.PrepareForm
api_type:
- COM
ms.assetid: 8f8ee2cb-1c2a-4958-b01e-2f4aab689f89
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d0d5d8fe13a3c192dc0b0a8ddc0f5f945fa16f15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321810"
---
# <a name="imapiformmgrprepareform"></a>IMAPIFormMgr::PrepareForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
下载用于打开的表单。
  
```cpp
HRESULT PrepareForm(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMINFO pfrmiInfo
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄, 在表单下载过程中显示。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_ulUIParam_参数。 
    
 _ulFlags_
  
> 实时用于控制如何下载表单的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示一个用户界面, 以提供状态或提示用户详细信息。 如果未设置此标志, 则不会显示任何用户界面。
    
 _pfrmiInfo_
  
> 实时指向要下载的表单的表单信息对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormMgr::P repareform**方法从用于打开的表单容器下载表单。 大多数窗体查看器不需要调用**PrepareForm**, 因为[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)和[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)方法都调用**PrepareForm**(如有必要)。 
  
您可以使用**PrepareForm**获取与表单关联的动态链接库 (dll) 和其他文件, 以对其进行修改。 如果将修改的表单加载回其表单容器, 则必须重新安装它。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)
  
[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)

