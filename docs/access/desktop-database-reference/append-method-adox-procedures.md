---
title: Append 方法 (ADOX Procedures)
TOCTitle: Append Method (ADOX Procedures)
ms:assetid: a93b31bb-e41a-5152-abe7-dd7c2b2fcd0a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249783(v=office.15)
ms:contentKeyID: 48546919
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 195cb08fb0b195b63cdddaa848554f24d028b498
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861874"
---
# <a name="append-method-adox-procedures"></a><span data-ttu-id="f1449-102">Append 方法 (ADOX Procedures)</span><span class="sxs-lookup"><span data-stu-id="f1449-102">Append Method (ADOX Procedures)</span></span>


<span data-ttu-id="f1449-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f1449-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="f1449-104">将新的 [Procedure](procedure-object-adox.md) 对象添加到 [Procedures](procedures-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="f1449-104">Adds a new [Procedure](procedure-object-adox.md) object to the [Procedures](procedures-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1449-105">语法</span><span class="sxs-lookup"><span data-stu-id="f1449-105">Syntax</span></span>

<span data-ttu-id="f1449-106">*过程*。追加*名称*，*命令*</span><span class="sxs-lookup"><span data-stu-id="f1449-106">*Procedures*.Append*Name*, *Command*</span></span>

## <a name="parameters"></a><span data-ttu-id="f1449-107">参数</span><span class="sxs-lookup"><span data-stu-id="f1449-107">Parameters</span></span>

  - <span data-ttu-id="f1449-108">*Name*</span><span class="sxs-lookup"><span data-stu-id="f1449-108">*Name*</span></span>

  - <span data-ttu-id="f1449-109">**String** 值，指定要创建并追加的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="f1449-109">A **String** value that specifies the name of the procedure to create and append.</span></span>

  - <span data-ttu-id="f1449-110">*Command*</span><span class="sxs-lookup"><span data-stu-id="f1449-110">*Command*</span></span>

  - <span data-ttu-id="f1449-111">一个 ADO [Command](command-object-ado.md) 对象，表示要创建并追加的过程。</span><span class="sxs-lookup"><span data-stu-id="f1449-111">An ADO [Command](command-object-ado.md) object that represents the procedure to create and append.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1449-112">备注</span><span class="sxs-lookup"><span data-stu-id="f1449-112">Remarks</span></span>

<span data-ttu-id="f1449-113">使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新过程。</span><span class="sxs-lookup"><span data-stu-id="f1449-113">Creates a new procedure in the data source with the name and attributes specified in the **Command** object.</span></span>

<span data-ttu-id="f1449-p101">如果用户指定的命令文本表示视图而非过程，则其行为取决于所使用的提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。</span><span class="sxs-lookup"><span data-stu-id="f1449-p101">If the command text that the user specifies represents a view rather than a procedure, the behavior is dependent upon the provider being used. **Append** will fail if the provider does not support persisting commands.</span></span>


> [!NOTE]
> <span data-ttu-id="f1449-116">使用 Microsoft Jet OLE DB 提供程序，将允许**Procedures**集合的**Append**方法，您可以在*命令*参数中指定**视图**，而不是**过程**。</span><span class="sxs-lookup"><span data-stu-id="f1449-116">When using the OLE DB Provider for Microsoft Jet, the **Procedures** collection **Append** method will allow you to specify a **View** rather than a **Procedure** in the *Command* parameter.</span></span> <span data-ttu-id="f1449-117">该 **View** 将添加到数据源，并将添加到 **Procedures** 集合。</span><span class="sxs-lookup"><span data-stu-id="f1449-117">The **View** will be added to the data source and will be added to the **Procedures** collection.</span></span> <span data-ttu-id="f1449-118">执行 **Append** 之后，如果刷新 **Procedures** 和 **Views** 集合，可以看见该 **View** 不再位于 **Procedures** 集合中，而是出现在 **Views** 集合中。</span><span class="sxs-lookup"><span data-stu-id="f1449-118">After the **Append**, if the **Procedures** and **Views** collections are refreshed, the **View** will no longer be in the **Procedures** collection and will appear in the **Views** collection.</span></span>


