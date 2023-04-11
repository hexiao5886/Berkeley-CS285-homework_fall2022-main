## Experiment 1
### small batch
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -dsa --exp_name q1_sb_no_rtg_dsa            # baseline
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -rtg -dsa --exp_name q1_sb_rtg_dsa          # reward-to-go
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -rtg --exp_name q1_sb_rtg_na                # standardize

### large batch
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -dsa --exp_name q1_lb_no_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -rtg -dsa --exp_name q1_lb_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -rtg --exp_name q1_lb_rtg_na

### Conclusion
See tensorboard for comparision, results show that
1) reward to go
2) standardize
3) large batch
are all superior!

## Experiment 2
To find the smallest batch size b* and largest learning rate r* that gets to optimum (maximum score of 1000)
学习率控制学习速度，批量大小控制学习方向的正确度，越大的学习率需要越大的批量大小来保证方向的正确性 
python cs285/scripts/run_hw2.py --env_name InvertedPendulum-v4 --ep_len 1000 --discount 0.9 -n 100 -l 2 -s 64 -b <b*> -lr <r*> -rtg --exp_name q2_b<b*>_r<r*>

python cs285/scripts/run_hw2.py --env_name InvertedPendulum-v4 --ep_len 1000 --discount 0.9 -n 100 -l 2 -s 64 -b 3000 -lr 8e-3 -rtg --exp_name q2_b3000_r8e-3

batch size | lr
1000 5e-3
5000 5e-3
5000 1e-2
5000 8e-3
3000 8e-3

## Experiment 3
python cs285/scripts/run_hw2.py --env_name LunarLanderContinuous-v2 --ep_len 1000 --discount 0.99 -n 100 -l 2 -s 64 -b 40000 -lr 0.005 --reward_to_go --nn_baseline --exp_name q3_b40000_r0.005
batch size too large to run on my personal PC
