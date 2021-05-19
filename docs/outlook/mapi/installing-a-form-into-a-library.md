---
title: 将表单安装到库中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 303c9dcb-f9b5-4cea-b5f2-3eba01aa3b09
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 08470a80153e42136922ae502252d83de0125512
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433141"
---
# <a name="installing-a-form-into-a-library"></a><span data-ttu-id="52593-103">将表单安装到库中</span><span class="sxs-lookup"><span data-stu-id="52593-103">Installing a Form into a Library</span></span>

  
  
<span data-ttu-id="52593-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52593-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52593-105">随 Windows SDK 提供的默认 MAPI 表单管理器不提供用于在各种表单库中安装表单的用户界面。</span><span class="sxs-lookup"><span data-stu-id="52593-105">The default MAPI form manager supplied with the Windows SDK does not provide a user interface for installing forms in the various form libraries.</span></span> <span data-ttu-id="52593-106">因此，您必须创建一个小型应用程序或一组详细的说明，以便用户安装表单。</span><span class="sxs-lookup"><span data-stu-id="52593-106">Because of this, you will have to create a small application — or detailed set of instructions — that users can use to install the form.</span></span>
  
<span data-ttu-id="52593-107">如果实现安装应用程序，则必须执行一系列操作才能将表单安装到文件夹的关联内容表中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52593-107">If you implement an installation application, the series of actions it must perform to install a form into a folder's associated contents table are as follows:</span></span>
  
1. <span data-ttu-id="52593-108">调用 [MAPIOpenFormMgr](mapiopenformmgr.md) 函数以打开表单管理器。</span><span class="sxs-lookup"><span data-stu-id="52593-108">Call the [MAPIOpenFormMgr](mapiopenformmgr.md) function to open the form manager.</span></span> 
    
2. <span data-ttu-id="52593-109">使用 [IMAPIFormMgr：：OpenFormContainer](imapiformmgr-openformcontainer.md) 或 [IMAPIFormMgr：：SelectFormContainer](imapiformmgr-selectformcontainer.md) 方法选择并打开表单的目标容器。</span><span class="sxs-lookup"><span data-stu-id="52593-109">Use [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md) or [IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md) method to select and open the target container for the form.</span></span> 
    
3. <span data-ttu-id="52593-110">使用 [IMAPIFormContainer：：InstallForm](imapiformcontainer-installform.md) 函数安装表单。</span><span class="sxs-lookup"><span data-stu-id="52593-110">Use the [IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md) function to install the form.</span></span> 
    
    <span data-ttu-id="52593-111">步骤 4 至步骤 6 适用于安装在本地表单库中：</span><span class="sxs-lookup"><span data-stu-id="52593-111">Steps 4 through 6 are for installation into a local form library:</span></span>
    
4. <span data-ttu-id="52593-112">如果安装在用户工作站上的本地表单库中，则复制所有文件到本地磁盘上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="52593-112">Copy all files to the appropriate place on the local disk, if installation is to the local form library on the user's workstation.</span></span> <span data-ttu-id="52593-113">如有必要，修改表单配置文件以反映组件的当前路径。</span><span class="sxs-lookup"><span data-stu-id="52593-113">If necessary, modify the form configuration file to reflect current paths of components.</span></span> <span data-ttu-id="52593-114">表单配置文件可以包含相对路径，在这种情况下，可能不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="52593-114">The form configuration file can contain relative paths, in which case this step may not be necessary.</span></span>
    
5. <span data-ttu-id="52593-115">完成相应的 OLE 注册步骤，将邮件类型与正在安装的表单服务器关联。</span><span class="sxs-lookup"><span data-stu-id="52593-115">Complete the appropriate OLE registration steps to associate the message type with the form server being installed.</span></span>
    
6. <span data-ttu-id="52593-116">如果表单已安装到本地表单库中，将表单的图标 (.ico) 和配置 (.cfg) 文件复制到 %WINDOWS%\FORMS\CONFIGS 目录中，以便表单在表单库损坏或删除时可以自动还原。</span><span class="sxs-lookup"><span data-stu-id="52593-116">If the form was installed into the local form library, copy the form's icon (.ico) and configuration (.cfg) files into the %WINDOWS%\FORMS\CONFIGS directory so the form can be automatically restored in case the form library is corrupted or deleted.</span></span> <span data-ttu-id="52593-117">建议执行此步骤，但不强制执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="52593-117">This step is recommended but not mandatory.</span></span>
    
> [!NOTE]
> <span data-ttu-id="52593-118">可以通过调用 [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) 函数来替换步骤 1 和步骤 2，从而简化到本地表单库的安装。</span><span class="sxs-lookup"><span data-stu-id="52593-118">You can simplify installation to a local form library by replacing steps 1 and 2 with a call to the [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="52593-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52593-119">See also</span></span>



[<span data-ttu-id="52593-120">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="52593-120">Developing MAPI Form Servers</span></span>](developing-mapi-form-servers.md)

