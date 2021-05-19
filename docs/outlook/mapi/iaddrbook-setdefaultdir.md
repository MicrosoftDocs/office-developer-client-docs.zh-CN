---
title: IAddrBookSetDefaultDir
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetDefaultDir
api_type:
- COM
ms.assetid: d5d60150-15e4-41ff-bfb0-0c67e2abcacc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ab01f189734ac30b4c027f4e5596c88031b5f99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341697"
---
# <a name="iaddrbooksetdefaultdir"></a><span data-ttu-id="c21f8-103">IAddrBook::SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="c21f8-103">IAddrBook::SetDefaultDir</span></span>

  
  
<span data-ttu-id="c21f8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c21f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c21f8-105">将指定的容器建立为默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="c21f8-105">Establishes the specified container as the default address book container.</span></span>
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="c21f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="c21f8-106">Parameters</span></span>

 <span data-ttu-id="c21f8-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c21f8-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="c21f8-108">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="c21f8-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="c21f8-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="c21f8-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="c21f8-110">[in]指向默认通讯簿容器的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c21f8-110">[in] A pointer to the entry identifier of the default address book container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c21f8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c21f8-111">Return value</span></span>

<span data-ttu-id="c21f8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c21f8-112">S_OK</span></span> 
  
> <span data-ttu-id="c21f8-113">已成功设置默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="c21f8-113">The default address book container was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c21f8-114">备注</span><span class="sxs-lookup"><span data-stu-id="c21f8-114">Remarks</span></span>

<span data-ttu-id="c21f8-115">客户端和服务提供商调用 **SetDefaultDir** 方法来建立一个新的默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="c21f8-115">Clients and service providers call the **SetDefaultDir** method to establish a new default address book container.</span></span> <span data-ttu-id="c21f8-116">默认容器是用户在首次打开通讯簿时在通讯簿中显示的容器。</span><span class="sxs-lookup"><span data-stu-id="c21f8-116">The default container is the container that the user sees displayed in the address book when the address book is first opened.</span></span> <span data-ttu-id="c21f8-117">**SetDefaultDir** 将默认容器保存为配置文件中的条目。</span><span class="sxs-lookup"><span data-stu-id="c21f8-117">**SetDefaultDir** saves the default container as an entry in the profile.</span></span> <span data-ttu-id="c21f8-118">容器保持为默认值，直到在同一会话中或其他会话中对 **SetDefaultDir** 进行另一次调用，或者容器被删除。</span><span class="sxs-lookup"><span data-stu-id="c21f8-118">The container remains as the default until either another call to **SetDefaultDir** is made in the same session or in another session, or the container is removed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c21f8-119">The [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property corresponds to the **Choose automatically setting** in the Address Book Options dialog.</span><span class="sxs-lookup"><span data-stu-id="c21f8-119">The [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property corresponds to the **Choose automatically** setting in the Address Book Options dialog.</span></span> <span data-ttu-id="c21f8-120">当此属性存在于 [IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件部分，并设置为 **true** 时，通讯簿对话框不再默认为 **SetDefaultDir** 指定的容器，而是选择 Microsoft Outlook 认为适合显示对话框的上下文的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="c21f8-120">When this property exists in the [IID_CAPONE_PROF](https://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx) profile section and is set to **true**, the Address Book dialog no longer defaults to the container specified by **SetDefaultDir**, but chooses an address book that Microsoft Outlook considers appropriate for the context in which the dialog was displayed.</span></span> <span data-ttu-id="c21f8-121">请注意，这可能会导致第三方通讯簿提供商体验不佳。</span><span class="sxs-lookup"><span data-stu-id="c21f8-121">Note that this may result in a poor experience for third-party address book providers.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c21f8-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c21f8-122">MFCMAPI reference</span></span>

<span data-ttu-id="c21f8-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c21f8-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c21f8-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="c21f8-124">**File**</span></span>|<span data-ttu-id="c21f8-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="c21f8-125">**Function**</span></span>|<span data-ttu-id="c21f8-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="c21f8-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c21f8-127">Abcontdlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c21f8-127">Abcontdlg.cpp</span></span>  <br/> |<span data-ttu-id="c21f8-128">CAbContDlg：：OnSetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="c21f8-128">CAbContDlg::OnSetDefaultDir</span></span>  <br/> |<span data-ttu-id="c21f8-129">MFCMAPI 使用 **SetDefaultDir** 方法将指定的通讯簿容器设置为默认容器。</span><span class="sxs-lookup"><span data-stu-id="c21f8-129">MFCMAPI uses the **SetDefaultDir** method to make the specified address book container the default one.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c21f8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c21f8-130">See also</span></span>



[<span data-ttu-id="c21f8-131">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="c21f8-131">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="c21f8-132">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="c21f8-132">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="c21f8-133">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="c21f8-133">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
  
[<span data-ttu-id="c21f8-134">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="c21f8-134">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="c21f8-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c21f8-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="c21f8-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c21f8-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

