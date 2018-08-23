---
title: IMAPIStatusSettingsDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.SettingsDialog
api_type:
- COM
ms.assetid: e931246e-7fff-4116-a9fc-f685988e21e8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a21feb474ef69da9ec8e36e06c8649b9d0f93981
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566703"
---
# <a name="imapistatussettingsdialog"></a><span data-ttu-id="a3e9b-103">IMAPIStatus::SettingsDialog</span><span class="sxs-lookup"><span data-stu-id="a3e9b-103">IMAPIStatus::SettingsDialog</span></span>

  
  
<span data-ttu-id="a3e9b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3e9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3e9b-105">显示使用户能够更改服务提供商的配置中 MAPI 实现的状态对象不支持此方法的属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-105">Displays a property sheet that enables the user to change a service provider's configuration This method is not supported in status objects that MAPI implements.</span></span>
  
```cpp
HRESULT SettingsDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a3e9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="a3e9b-106">Parameters</span></span>

 <span data-ttu-id="a3e9b-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a3e9b-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="a3e9b-108">[in]配置属性表的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-108">[in] A handle to the parent window of the configuration property sheet.</span></span>
    
 <span data-ttu-id="a3e9b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a3e9b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="a3e9b-110">[in]位掩码的标志的控件显示的属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-110">[in] A bitmask of flags that controls the display of the property sheet.</span></span> <span data-ttu-id="a3e9b-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="a3e9b-111">The following flag can be set:</span></span>
    
<span data-ttu-id="a3e9b-112">UI_READONLY</span><span class="sxs-lookup"><span data-stu-id="a3e9b-112">UI_READONLY</span></span> 
  
> <span data-ttu-id="a3e9b-113">建议的提供程序不应使用户能够更改配置属性。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-113">Suggests that the provider should not enable users to change configuration properties.</span></span> <span data-ttu-id="a3e9b-114">此标志为只建议;可以忽略它。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-114">This flag is only a suggestion; it can be ignored.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a3e9b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a3e9b-115">Return value</span></span>

<span data-ttu-id="a3e9b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3e9b-116">S_OK</span></span> 
  
> <span data-ttu-id="a3e9b-117">配置属性表显示成功。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-117">The configuration property sheet was displayed successfully.</span></span>
    
<span data-ttu-id="a3e9b-118">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="a3e9b-118">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="a3e9b-119">状态对象不支持此方法，由 STATUS_SETTINGS_DIALOG 标志**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中不存在。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-119">The status object does not support this method, as indicated by the absence of the STATUS_SETTINGS_DIALOG flag in the **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a3e9b-120">注解</span><span class="sxs-lookup"><span data-stu-id="a3e9b-120">Remarks</span></span>

<span data-ttu-id="a3e9b-121">**IMAPIStatus::SettingsDialog**方法显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-121">The **IMAPIStatus::SettingsDialog** method displays a configuration property sheet.</span></span> <span data-ttu-id="a3e9b-122">所有服务提供商应都支持**留待**方法，但不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-122">All service providers should support the **SettingsDialog** method, but it is not required.</span></span> <span data-ttu-id="a3e9b-123">服务提供商可以实现自己的属性表或使用支持对象的[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法中提供的实现。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-123">Service providers can implement their own property sheets or use the implementation supplied in the support object's [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method.</span></span> <span data-ttu-id="a3e9b-124">**DoConfigPropsheet**生成读/写属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-124">**DoConfigPropsheet** builds a read/write property sheet.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a3e9b-125">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="a3e9b-125">Notes to implementers</span></span>

<span data-ttu-id="a3e9b-126">如果远程传输提供程序的任何设置，它应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3e9b-126">If a remote transport provider has any settings, it should do the following:</span></span>
  
- <span data-ttu-id="a3e9b-127">打开传输提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-127">Open the transport provider's profile section.</span></span>
    
- <span data-ttu-id="a3e9b-128">获取从配置文件的传输提供程序的属性设置。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-128">Get the transport provider's property settings from the profile.</span></span>
    
- <span data-ttu-id="a3e9b-129">在对话框中显示的属性设置。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-129">Display the property settings in a dialog box.</span></span>
    
- <span data-ttu-id="a3e9b-130">如果在对话框中，编辑属性设置的检查新的设置有效，并将它们存储返回在传输提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-130">If the dialog box allows editing of the property settings, check that the new settings are valid and store them back in the transport provider's profile section.</span></span>
    
- <span data-ttu-id="a3e9b-131">返回 S_OK 或在前面步骤中返回的任何错误值。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-131">Return S_OK, or any error values returned during the preceding steps.</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="a3e9b-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a3e9b-132">Notes to callers</span></span>

<span data-ttu-id="a3e9b-133">属性表通过**留待**显示可用于执行各种任务，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3e9b-133">You can use the property sheet displayed through **SettingsDialog** to perform a variety of tasks, such as the following:</span></span> 
  
- <span data-ttu-id="a3e9b-134">指定默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-134">Specify a default message store.</span></span>
    
- <span data-ttu-id="a3e9b-135">指定传输顺序。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-135">Specify a transport order.</span></span>
    
- <span data-ttu-id="a3e9b-136">指定用于浏览默认通讯簿容器。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-136">Specify a default address book container for browsing.</span></span>
    
- <span data-ttu-id="a3e9b-137">指定搜索顺序解决不明确的名称。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-137">Specify a search order for resolving ambiguous names.</span></span>
    
- <span data-ttu-id="a3e9b-138">指定默认个人通讯簿。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-138">Specify a default personal address book.</span></span>
    
<span data-ttu-id="a3e9b-139">为读/写，只读的的属性表或混合的权限，具体取决于该属性，可以实现服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-139">Service providers can implement property sheets that are read/write, read-only, or a mixture of permissions, depending on the property.</span></span> <span data-ttu-id="a3e9b-140">服务提供商可以通过设置属性限制单个属性实现不同的权限。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-140">Service providers can implement different permissions on individual properties by setting property restrictions.</span></span> <span data-ttu-id="a3e9b-141">属性表的默认模式是可读写。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-141">The default mode for property sheets is read/write.</span></span> <span data-ttu-id="a3e9b-142">您可以通过在您调用**留待**中设置 UI_READONLY 标志请求只读属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-142">You can request read-only property sheets by setting the UI_READONLY flag in your calls to **SettingsDialog**.</span></span> <span data-ttu-id="a3e9b-143">能够实现只读属性页的服务提供商可以这样做。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-143">Service providers that are able to implement read-only property sheets can do so.</span></span> <span data-ttu-id="a3e9b-144">但是，因为某些服务提供程序无法重写默认模式，您必须是准备处理任一类型的属性表。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-144">However, because some service providers cannot override the default mode, you must be prepared to handle property sheets of either type.</span></span> 
  
<span data-ttu-id="a3e9b-145">由于始终在此操作中涉及的用户界面，则仅交互式客户端应调用**留待**。</span><span class="sxs-lookup"><span data-stu-id="a3e9b-145">Because a user interface is always involved in this operation, only interactive clients should call **SettingsDialog**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3e9b-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e9b-146">See also</span></span>



[<span data-ttu-id="a3e9b-147">IMAPISupport::DoConfigPropsheet</span><span class="sxs-lookup"><span data-stu-id="a3e9b-147">IMAPISupport::DoConfigPropsheet</span></span>](imapisupport-doconfigpropsheet.md)
  
[<span data-ttu-id="a3e9b-148">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3e9b-148">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="a3e9b-149">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a3e9b-149">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

