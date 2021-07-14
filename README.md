# Kira-s
# Class torch.nn.Module

import torch.nn as nn
import torch.nn.functional as F

#Modules can also contain other Modules, allowing to nest them in a tree structure. You can assign the submodules as regular attributes:

class Model(nn.Module):
    def __init__(self):
        super(Model, self).__init__()
        self.conv1 = nn.Conv2d(1, 20, 5)
        self.conv2 = nn.Conv2d(20, 20, 5)

    def forward(self, x):
        x = F.relu(self.conv1(x))
        return F.relu(self.conv2(x))
        
# Class torch.nn.Conv1d(in_channels, out_channels, kernel_size, stride=1, padding=0, dilation=1, groups=1, bias=True, padding_mode='zeros', device=None, dtype=None)
