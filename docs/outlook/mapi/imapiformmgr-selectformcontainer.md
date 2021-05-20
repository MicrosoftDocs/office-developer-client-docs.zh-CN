---
title: IMAPIFormMgrSelectFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: c33daad6-52c4-4968-ac56-415178c9bf12
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bfddc24e6a9c7cf8bdeae1e5ea730ecdb116f564
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428590"
---
# <a name="imapiformmgrselectformcontainer"></a>IMAPIFormMgr::SelectFormContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示一个对话框，允许用户选择表单容器，并返回用户选择的容器对象的接口。
  
```cpp
HRESULT SelectFormContainer(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]所显示对话框的父窗口的句柄。 
    
 _ulFlags_
  
> [in]一个标志位掩码，用于控制如何选择表单库 (即，如何选择表单容器) 。 可以设置以下标志：
    
MAPIFORM_SELECT_ALL_REGISTRIES 
  
> 可以从所有容器进行选择。 这是默认选择类型。 
    
MAPIFORM_SELECT_FOLDER_REGISTRY_ONLY 
  
> 只能从文件夹容器进行选择。
    
MAPIFORM_SELECT_NON_FOLDER_REGISTRY_ONLY 
  
> 只能从未与文件夹关联的容器中进行选择。
    
 _lppfcnt_
  
> [out]指向返回接口的指针的指针。 此接口用于用户选择的容器对象。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

表单查看器通常调用 **IMAPIFormMgr：：SelectFormContainer** 方法来选择将表单安装到的表单容器。 **SelectFormContainer** 不能用于选择本地表单容器，该容器的值HFRMREG_LOCAL。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnSelectFormContainer  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：SelectFormContainer** 方法在呈现表单容器内容之前选择表单容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

