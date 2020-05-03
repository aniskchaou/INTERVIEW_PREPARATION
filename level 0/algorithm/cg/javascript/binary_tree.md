
    function searchIter(data) {
       var  currNode = this.root;
       while (currNode !== null) {
          if (currNode.data === data) {
             // Found the element!
             return true;
          } else if (data < currNode.data) {
             // Go Left as data is smaller than parent
             currNode = currNode.left;
          } else {
             // Go right as data is greater than parent
             currNode = currNode.right;
          }
       }
       return false;
    }
