---
title: "如何： 使用 Try Catch 區塊攔截例外狀況"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a72a21085c37bed4d84518810f69a013d515189
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="fd20a-102">如何使用 try/catch 區塊攔截例外狀況</span><span class="sxs-lookup"><span data-stu-id="fd20a-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="fd20a-103">將可能擲回例外狀況的程式碼區段放在 `try` 區塊中，並將處理例外狀況的程式碼放在 `catch` 區塊中。</span><span class="sxs-lookup"><span data-stu-id="fd20a-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="fd20a-104">`catch` 區塊為一系列的陳述式，以關鍵字 `catch` 開頭，後面接著例外狀況類型和要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="fd20a-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="fd20a-105">下列程式碼範例使用 `try`/`catch` 區塊攔截可能的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="fd20a-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="fd20a-106">`Main` 方法包含內存 <xref:System.IO.StreamReader> 陳述式的 `try` 區塊，該陳述式可開啟名為 `data.txt` 的資料檔案，並寫入檔案中的字串。</span><span class="sxs-lookup"><span data-stu-id="fd20a-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="fd20a-107">`try` 區塊後面接著 `catch` 區塊，該區塊會攔截 `try` 區塊所產生的任何例外狀況。</span><span class="sxs-lookup"><span data-stu-id="fd20a-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="fd20a-108">Common Language Runtime 會攔截 catch 區塊未攔截的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="fd20a-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="fd20a-109">根據執行階段的設定方式，可能會發生下列其中一種情況：顯示偵錯對話方塊、程式停止執行並顯示內含例外狀況資訊的對話方塊，或錯誤印出至 STDERR。</span><span class="sxs-lookup"><span data-stu-id="fd20a-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="fd20a-110">幾乎任何一行程式碼都可能造成例外狀況，尤其是 Common Language Runtime 本身擲回的例外狀況，例如 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="fd20a-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="fd20a-111">大多數應用程式都不需要處理這些例外狀況，但您應該在撰寫供他人使用的程式庫時留意這點可能性。</span><span class="sxs-lookup"><span data-stu-id="fd20a-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="fd20a-112">如需何時在 Try 區塊中設定程式碼的建議，請參閱[例外狀況的最佳做法](best-practices-for-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fd20a-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd20a-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd20a-113">See Also</span></span>  
[<span data-ttu-id="fd20a-114">例外狀況</span><span class="sxs-lookup"><span data-stu-id="fd20a-114">Exceptions</span></span>](index.md)