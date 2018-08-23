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
ms.openlocfilehash: 68cca0b483aca91001f8ee71289f4b1673fb2888
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564652"
---
# <a name="iaddrbooksetdefaultdir"></a><span data-ttu-id="aa654-103">IAddrBook::SetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="aa654-103">IAddrBook::SetDefaultDir</span></span>

  
  
<span data-ttu-id="aa654-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa654-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa654-105">建立默认通讯簿容器为指定的容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-105">Establishes the specified container as the default address book container.</span></span>
  
```cpp
HRESULT SetDefaultDir(
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="aa654-106">参数</span><span class="sxs-lookup"><span data-stu-id="aa654-106">Parameters</span></span>

 <span data-ttu-id="aa654-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="aa654-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="aa654-108">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="aa654-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="aa654-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="aa654-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="aa654-110">[in]指向默认通讯簿容器的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aa654-110">[in] A pointer to the entry identifier of the default address book container.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aa654-111">返回值</span><span class="sxs-lookup"><span data-stu-id="aa654-111">Return value</span></span>

<span data-ttu-id="aa654-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa654-112">S_OK</span></span> 
  
> <span data-ttu-id="aa654-113">已成功设置默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-113">The default address book container was successfully set.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aa654-114">注解</span><span class="sxs-lookup"><span data-stu-id="aa654-114">Remarks</span></span>

<span data-ttu-id="aa654-115">客户端和服务提供商调用**SetDefaultDir**方法建立新的默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-115">Clients and service providers call the **SetDefaultDir** method to establish a new default address book container.</span></span> <span data-ttu-id="aa654-116">默认容器是首次打开通讯簿时显示在通讯簿中的用户看到的容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-116">The default container is the container that the user sees displayed in the address book when the address book is first opened.</span></span> <span data-ttu-id="aa654-117">**SetDefaultDir**将默认容器保存为配置文件中的条目。</span><span class="sxs-lookup"><span data-stu-id="aa654-117">**SetDefaultDir** saves the default container as an entry in the profile.</span></span> <span data-ttu-id="aa654-118">容器将保持为默认值，直到在同一个会话或另一个会话中进行**SetDefaultDir**到另一个呼叫，或者删除容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-118">The container remains as the default until either another call to **SetDefaultDir** is made in the same session or in another session, or the container is removed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="aa654-119">[PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md)属性对应于在通讯簿选项对话框的**自动选择**设置。</span><span class="sxs-lookup"><span data-stu-id="aa654-119">The [PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY](pidtagaddressbookchoosedirectoryautomatically-canonical-property.md) property corresponds to the **Choose automatically** setting in the Address Book Options dialog.</span></span> <span data-ttu-id="aa654-120">不再通讯簿对话框时该属性存在[IID_CAPONE_PROF](http://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx)配置文件一节，但将设置为**true**，默认为**SetDefaultDir**，指定的容器，但选择 Microsoft Outlook 会认为通讯簿适用于在其中显示对话框中的上下文。</span><span class="sxs-lookup"><span data-stu-id="aa654-120">When this property exists in the [IID_CAPONE_PROF](http://msdn.microsoft.com/library/281aabc3-9656-299c-4c78-7733dc71050a%28Office.15%29.aspx) profile section and is set to **true**, the Address Book dialog no longer defaults to the container specified by **SetDefaultDir**, but chooses an address book that Microsoft Outlook considers appropriate for the context in which the dialog was displayed.</span></span> <span data-ttu-id="aa654-121">请注意，这可能会导致不好的体验的第三方通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="aa654-121">Note that this may result in a poor experience for third-party address book providers.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="aa654-122">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="aa654-122">MFCMAPI reference</span></span>

<span data-ttu-id="aa654-123">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="aa654-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="aa654-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="aa654-124">**File**</span></span>|<span data-ttu-id="aa654-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="aa654-125">**Function**</span></span>|<span data-ttu-id="aa654-126">**Comment**</span><span class="sxs-lookup"><span data-stu-id="aa654-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa654-127">Abcontdlg.cpp</span><span class="sxs-lookup"><span data-stu-id="aa654-127">Abcontdlg.cpp</span></span>  <br/> |<span data-ttu-id="aa654-128">CAbContDlg::OnSetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="aa654-128">CAbContDlg::OnSetDefaultDir</span></span>  <br/> |<span data-ttu-id="aa654-129">MFCMAPI 使用**SetDefaultDir**方法将一个默认的指定在通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="aa654-129">MFCMAPI uses the **SetDefaultDir** method to make the specified address book container the default one.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa654-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa654-130">See also</span></span>



[<span data-ttu-id="aa654-131">IAddrBook::GetDefaultDir</span><span class="sxs-lookup"><span data-stu-id="aa654-131">IAddrBook::GetDefaultDir</span></span>](iaddrbook-getdefaultdir.md)
  
[<span data-ttu-id="aa654-132">IAddrBook::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="aa654-132">IAddrBook::GetSearchPath</span></span>](iaddrbook-getsearchpath.md)
  
[<span data-ttu-id="aa654-133">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="aa654-133">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
  
[<span data-ttu-id="aa654-134">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="aa654-134">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="aa654-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="aa654-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="aa654-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="aa654-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

