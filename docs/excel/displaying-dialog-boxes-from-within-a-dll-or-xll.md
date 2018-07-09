---
title: 显示对话框从 DLL 或 XLL 中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll [excel 2007]，显示对话框中，对话框 [Excel 2007]，显示从 DLL 或 XLL，显示对话框从 Dll [Excel 2007]
localization_priority: Normal
ms.assetid: e77ac555-331d-41c8-a000-7b178959754d
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: afb21125bc54a2607a997c7b2f7c73ef2f528f28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773651"
---
# <a name="displaying-dialog-boxes-from-within-a-dll-or-xll"></a><span data-ttu-id="4827d-104">显示对话框从 DLL 或 XLL 中</span><span class="sxs-lookup"><span data-stu-id="4827d-104">Displaying Dialog Boxes from Within a DLL or XLL</span></span>

 <span data-ttu-id="4827d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4827d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4827d-106">若要显示 Win32 对话框中使用，例如 Windows SDK 函数**DialogBox**，首先必须适用于 Excel 获取完整的 32 位实例和主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="4827d-106">To display a Win32 dialog box using, for example, the Windows SDK function **DialogBox**, you must first obtain the full 32-bit instance and main window handles for Excel.</span></span> <span data-ttu-id="4827d-107">有关详细信息，请参阅[访问 Excel 实例，主窗口句柄](how-to-access-excel-instance-and-main-window-handles.md)。</span><span class="sxs-lookup"><span data-stu-id="4827d-107">For more information, see [Access Excel Instance and Main Window Handles](how-to-access-excel-instance-and-main-window-handles.md).</span></span> 
  
<span data-ttu-id="4827d-108">假定您的项目包含对话框资源，必须执行以下几个步骤以设置为的新显示的对话框中的消息处理例程并恢复 Excel 邮件处理例程时关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="4827d-108">Assuming your project contains the dialog box resource, you must take several steps to set the message-handling routine to that of the newly displayed dialog box and to restore the Excel message handling routine when the dialog box is closed.</span></span> <span data-ttu-id="4827d-109">通用项目中的示例命令[fShowDialog](fshowdialog.md)演示了 Windows 函数以正确执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4827d-109">The example command [fShowDialog](fshowdialog.md) in the Generic project demonstrates the use of the Windows functions to do this correctly.</span></span> 
  
<span data-ttu-id="4827d-110">您还可以显示对话框，而无需使用 Windows SDK 函数中使用 C API。</span><span class="sxs-lookup"><span data-stu-id="4827d-110">You can also display dialog boxes using the C API without having to use Windows SDK functions.</span></span> <span data-ttu-id="4827d-111">但是，C API 的对话框框功能是非常有限与 Windows、 Visual Basic for Applications (VBA) 或 Microsoft 基础类 (MFC) 的比较。</span><span class="sxs-lookup"><span data-stu-id="4827d-111">However, the dialog box capabilities of the C API are very limited compared with those of Windows, Visual Basic for Applications (VBA), or the Microsoft Foundation Classes (MFC).</span></span> <span data-ttu-id="4827d-112">（例如，C API 对话框始终是有模式）。</span><span class="sxs-lookup"><span data-stu-id="4827d-112">(For example, C API dialog boxes are always modal).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4827d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4827d-113">See also</span></span>



[<span data-ttu-id="4827d-114">创建 xll</span><span class="sxs-lookup"><span data-stu-id="4827d-114">Creating XLLs</span></span>](creating-xlls.md)
  
[<span data-ttu-id="4827d-115">开发 Dll</span><span class="sxs-lookup"><span data-stu-id="4827d-115">Developing DLLs</span></span>](developing-dlls.md)
  
[<span data-ttu-id="4827d-116">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="4827d-116">Access Excel Instance and Main Window Handles</span></span>](how-to-access-excel-instance-and-main-window-handles.md)
  
[<span data-ttu-id="4827d-117">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="4827d-117">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

