function closestToZero(ts) {
        if (ts.length == 0) return 0;

        var closest = ts[0];
    
        for (var i=0 ; i<ts.length;i++) {
            var abs = Math.abs(ts[i]);
            var absClosest = Math.abs(closest);

            if (abs < absClosest) {
                closest = ts[i];
            } else if (abs == absClosest && closest < 0) {
                closest = ts[i];
            }
        }
        return closest;
    }